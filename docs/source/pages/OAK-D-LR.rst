OAK-D LR
========

`Buy it on Luxonis shop <https://shop.luxonis.com/collections/oak-cameras-1/products/oak-d-lr>`__

.. thumbnail:: /_static/images/OAK-D-LR/oak-d-lr-bottom.jpg

Overview
********

The **OAK-D Long Range** (OAK-D LR) was designed to provide an accurate **short range and long range stereo depth perception**. This works by having up to 3 stereo depth pairs at different baseline distances.
One can also easily change the `M12 lenses <M12 selectable FOV>`__ for the cameras, which also affects the min/max distance of stereo depth perception (`additional info <https://docs.luxonis.com/projects/api/en/latest/tutorials/configuring-stereo-depth/#depth-from-disparity>`__).

It has **3** horizontally aligned :ref:`AR0234` global shutter color cameras, which have different distances between each other, and allow for 3 different stereo baseline camera pairs (5cm, 10cm and 15cm baseline distances).

The OAK-D LR leverages our :ref:`OAK-SoM-Pro <bw2099>` to make a overall compact design. The use of the SoM reduces the
design's scale, making it easier to mount or fit in various robotic processes. The design is also `open-source <https://github.com/luxonis/depthai-hardware/tree/master/BC2087_OAK-D-LR>`__,
allowing for any necessary `modifications <https://docs.luxonis.com/projects/hardware/en/latest/pages/guides/integrating_depthai_into_products.html>`__.

Hardware specifications
***********************

For communication and power, the OAK-D LR camera uses **either**:

- USB-C cable - it supports both USB2 and USB3 (5Gbps / 10Gbps).
- Power-over-Ethernet (PoE) - it offers full 802.3af and Class 3 PoE compliance with 1000BASE-T speeds (1 Gbps). A :ref:`PoE injector/switch <Powering PoE devices>` is required to power the device.

.. list-table::
   :header-rows: 1

   * - Camera Specs
     - Stereo pair / Color
   * - Sensor
     - :ref:`AR0234` (**color**, PY078)
   * - DFOV / HFOV / VFOV
     - 100° / 82° / 56°
   * - Resolution
     - 2.3MP (1920x1200)
   * - Focus
     - M12 (FF): 45cm - ∞
   * - Lens size
      - 1/2.5 inch
   * - Max Framerate
     - 60 FPS (1200P)
   * - Pixel size
     - 3µm x 3µm
..
   * - F-number
     - 2.0 ±5%
   * - Lens size
     - 1/4 inch
   * - Effective Focal Length
     - 2.35mm


Stereo depth perception
***********************

This OAK camera has a baseline of 5 cm, 10 cm, and 15 cm. Baseline distance is the distance between the left and the right stereo camera. Since we have 3 camera sensors on the OAK-D-LR,
we also have 3 baseline distances, and 3 potential stereo pairs. We measured the accuracy of the 15 cm stereo pair (the left-most and right-most camera).

* `Depth range <https://docs.luxonis.com/projects/api/en/latest/tutorials/configuring-stereo-depth/#move-the-camera-closer-to-the-object>`__: 20cm - 16m
* :ref:`Stereo Depth Accuracy`:

    * 20cm - 6m: below 2% absolute depth error
    * 6m - 8m: below 3% absolute depth error
    * 8m-12m: below 4% absolute depth error

Theoretical depth accuracy
**************************

As M12 lenses are swappable, user can easily change lenses to achieve **wider FOV**, or **longer depth perception** (narrower FOV):

.. list-table:: Maximum depth perception based on lens/accuracy
   :header-rows: 1

   * - HFOV [°]
     - < 2% depth error
     - < 4% depth error
     - < 8% depth error
     - MinZ
   * - 10
     - 54.9 m
     - 137.2 m
     - 274.3 m
     - 1.92 m
   * - 20
     - 27.2 m
     - 68.1 m
     - 136.1 m
     - 95 cm
   * - 30
     - 17.9 m
     - 44.8 m
     - 89.6 m
     - 63 cm
   * - 40
     - 13.2 m
     - 33.0 m
     - 65.9 m
     - 46 cm
   * - 50
     - 10.3 m
     - 25.7 m
     - 51.5 m
     - 36 cm
   * - 60
     - 8.3 m
     - 20.8 m
     - 41.6 m
     - 29 cm
   * - 70
     - 6.9 m
     - 17.1 m
     - 34.3 m
     - 24 cm
   * - 80
     - 5.7 m
     - 14.3 m
     - 28.6 m
     - 21 cm
   * - **82**
     - **5.5 m**
     - **13.8 m**
     - **27.6 m**
     - **20 cm**
   * - 90
     - 4.8 m
     - 12.0 m
     - 24.0 m
     - 17 cm
   * - 100
     - 4.0 m
     - 10.1 m
     - 20.1 m
     - 14 cm

**Note:** we haven't tested all of these combinations, but calculated `theoretical depth error <https://docs.google.com/spreadsheets/d/1ymn-0D4HcCbzYP-iPycj_PIdSwmrLenlGryuZDyA4rQ/edit#gid=0>`__
and interpolated those values with our previous real-world tests when enabling subpixel disparity:

- ``< 2% error`` - 20th disparity pixel, which has 5% full-pixel error (~2% with subpixel enabled)
- ``< 4% error`` - 8th disparity pixel, which has 12.5% full-pixel error (~4% with subpixel enabled)
- ``< 8% error`` - 4th disparity pixel, which has 25% full-pixel error (~10% with subpixel enabled)

Maximum depth was calculated by using the large (15cm) baseline, while MinZ was calculated by using the small (5cm) baseline of the OAK-D-LR. You can further decrease MinZ by lowering the resolution,
or using disparity shift (`docs here <https://docs.luxonis.com/projects/api/en/latest/tutorials/configuring-stereo-depth/#how-to-get-lower-minz>`__). MinZ values are already using Extended Disparity Mode.

.. include:: /pages/rvc/includes/rvc2_inside.rst

Dimensions and Weight
*********************

..
   .. thumbnail:: /_static/images/BW1098OAK/oak-d-dimensions.png
* Width: 202 mm
* Height: 44 mm
* Length: 40 mm
* Weight: 415g

.. thumbnail:: /_static/images/OAK-D-LR/dimensions.png

.. include:: /pages/includes/imu_bno085.rst

..
   .. include:: /pages/includes/depth_75_800P.rst

..
   Getting started
   ***************

   The OAK-D is powered via USB Type-C or from a 5V, 5.5m x 2.5mm barrel jack. USB3 5Gbps speeds are standard for streaming video or data 
   from the device. With cameras and the :ref:`OAK-SoM`, total power consumption usually stays below the 900ma specification of USB 3, but Type-C 
   power of 1.5A or greater is recommended.

   Interfacing with the :ref:`OAK-SoM` is also possible with OAK-D connector pads J4, J5, and J6. These pads are designed for the Amphenol/FCI 
   20021121-00010T1LF or equivalent. Please refer to the schematics for pinout information.

   The reset button is not populated by default on the OAK-D, but can be added. Alternatively, the :ref:`OAK-SoM`can be reset by shorting RST to ground.

   The 5V LED indicates 5V power is present on the PCBA. The PG LED indicates "power good" from the OAK-SoM. The "RUN"
   LED indicates that the OAK-SoM is not in reset.

..
   Brochures
   *********

   * `Brochure <https://github.com/luxonis/depthai-hardware/tree/master/BC2087_OAK-D-LR/Datasheet/OAK-D_brochure.pdf>`__
   * `Datasheet <https://github.com/luxonis/depthai-hardware/tree/master/BC2087_OAK-D-LR/Datasheet/OAK-D_Datasheet.pdf>`__

.. include:: /pages/includes/rvc2_power_consumption_poe.rst

.. include:: /pages/includes/rvc2_operating_temp.rst

3D Models
*********

- PCBA Board `STEP here <https://oak-files.fra1.cdn.digitaloceanspaces.com/OAK-D-LR/OAK-D-LR_PCBA.STEP>`__
- Enclosure `STEP here <https://oak-files.fra1.cdn.digitaloceanspaces.com/OAK-D-LR/OAK-D-LR_Enclosure.STEP>`__
- Enclosure `STL here <https://oak-files.fra1.cdn.digitaloceanspaces.com/OAK-D-LR/OAK-D-LR_Enclosure.STL>`__

Files
*****

* `Altium project files <https://github.com/luxonis/depthai-hardware/tree/master/BC2087_OAK-D-LR/PCB>`__
* `Assembly Drawing <https://github.com/luxonis/depthai-hardware/blob/master/BC2087_OAK-D-LR/Docs/Assembly%20Drawing%20PDF/Production.PDF>`__
* `Assembly Outputs <https://github.com/luxonis/depthai-hardware/tree/master/BC2087_OAK-D-LR/Docs/Assembly%20Outputs>`__
* `Fabrication Drawing <https://github.com/luxonis/depthai-hardware/blob/master/BC2087_OAK-D-LR/Docs/Fabrication%20Drawing%20PDF/Production.PDF>`__
* `Fabrication Outputs <https://github.com/luxonis/depthai-hardware/tree/master/BC2087_OAK-D-LR/Docs/Fabrication%20Outputs>`__
* `Schematic <https://github.com/luxonis/depthai-hardware/blob/master/BC2087_OAK-D-LR/Docs/Schematic%20PDF/Production.PDF>`__

.. include::  /pages/includes/footer-short.rst
