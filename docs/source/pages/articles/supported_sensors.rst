.. _supported_sensors:

Supported sensors
=================

.. toctree::
  :hidden:
  :glob:
  :maxdepth: 0

  sensors/*

DepthAI firmware has to have sensor configuration in order to support the given camera sensor. Currently, we support sensor
configurations out-of-the-box (in firmware) for the camera sensors listed below.

.. list-table:: Supported sensors by DepthAI
   :header-rows: 1

   * - Sensor
     - Status
     - Shutter
     - Resolution
     - Notes
   * - :ref:`IMX378`
     - Fully integrated
     - rolling
     - 4056x3040
     - Used in most OAK cameras
   * - :ref:`OV9282`
     - Fully integrated
     - global
     - 1280x800
     - Used in most OAK-D cameras
   * - :ref:`IMX214`
     - Fully integrated
     - rolling
     - 4208x3120
     - Used in :ref:`OAK-D-Lite` as color camera
   * - OV7750, :ref:`OV7251`
     - Fully integrated
     - global
     - 640x480
     - OV7251 used in :ref:`OAK-D-Lite` as stereo pair
   * - :ref:`IMX477`
     - Fully integrated
     - rolling
     - 4056x3040
     - `FFC module shop <https://shop.luxonis.com/collections/modular-cameras/products/oak-ffc-imx477>`__
   * - OV9281
     - Fully integrated
     - global
     - 1280x800
     -
   * - :ref:`OV9782`
     - Fully integrated
     - global
     - 1280x800
     - `FFC module shop <https://shop.luxonis.com/collections/modular-cameras/products/oak-ffc-ov9782-22-pin>`__
   * - :ref:`AR0234`
     - Fully integrated (mono and color)
     - global
     - 1920x1200
     - `FFC module shop <https://shop.luxonis.com/collections/modular-cameras/products/ar0234>`__
   * - IMX296
     - Fully integrated
     - global
     - 1456x1088
     - `RPi Global Shutter Cam <https://www.raspberrypi.com/products/raspberry-pi-global-shutter-camera/>`__ - **Note:** `See this <https://discuss.luxonis.com/d/1460-rpi-high-quality-camera-with-oak-ffc-baseboard>`__
   * - IMX219
     - Initially integrated
     - rolling
     - 3280x2464
     - Requires ``imx219`` branch. `RPi Cam V2 <https://www.raspberrypi.com/products/camera-module-v2/>`__ works with FFC via `Adapter <https://shop.luxonis.com/products/oak-ffc-uc244-2>`__
   * - IMX708
     - Initially integrated
     - rolling
     - 4608x2592
     - `RPi Cam V3 <https://www.raspberrypi.com/products/camera-module-3/>`__ works with FFC via `Adapter <https://shop.luxonis.com/products/oak-ffc-uc244-2>`__
   * - IMX577
     - Fully integrated
     - rolling
     - 4056x3040
     - Initially tested, similar to IMX477
   * - :ref:`IMX582`
     - Initially tested
     - rolling
     - 8000x6000
     - 5312x6000 supported
   * - IMX363, IMX362
     - Driver/tuning available for IMX363
     - rolling
     - 4048x3024
     -
   * - OV12895, OV12890
     - Driver/tuning available for OV12895
     - rolling
     - 4096x3072
     -
   * - IMX380
     - Initially tested and integrated
     - rolling
     - 4056x3040
     -
   * - OV5645
     - Initially tested and integrated
     - rolling
     - 2592x1944
     -
   * - IMX283
     - Initially integrated
     - rolling
     - 5496x3672
     - Huge sensor, works on ``develop`` branch, `FFC cam module <https://www.arducam.com/product/arducam-20mp-imx283-camera-module-with-m12-mount-lens-and-adapter-board-for-depthai/>`__
   * - :ref:`IMX462`
     - Initially integrated
     - rolling
     - 1920x1080
     - STARVIS, works on ``develop`` branch

.. list-table:: Driver/tuning available but not yet tested/integrated
   :header-rows: 1

   * - Sensor
     - Status
     - Shutter
     - Resolution
     - Notes
   * - IMX334
     - Not tested
     - rolling
     - 3840x2160
     -
   * - IMX390
     - Not tested
     - rolling
     - 1937x1217
     -
   * - IMX412
     - Not tested
     - rolling
     - 4056x3040
     -
   * - SC2232H
     - Not tested
     - rolling
     - 1936x1086
     -
   * - OV2735
     - Not tested
     - rolling
     - 1920x1080
     -
   * - SC5335
     - Not tested
     - rolling
     - 2592x1944
     -
   * - SC8238
     - Not tested
     - rolling
     - 3840x2160
     -

**Interested in a "Not tested" sensor, or a sensor not listed above?** Please send an email to support@luxonis.com.

Already built CCMs
==================

Here's the list of already built Compact Camera Modules (CCMs) by `Arducam <https://www.arducam.com/>`__.
MOQ for OAK camera product with a custom configuration of CCMs from the listed below is 100 units. Please send an
email to support@luxonis.com if that's of interest.

NFOV = Normal FOV, WFOV = Wide FOV. NoIR = No IR filter, IR = IR filter. FF = Fixed-Focus, AF = Auto-Focus.

Sunny style long FPC
--------------------

* :ref:`IMX378`

  * NFOV (AF/FF) - 81° DFOV, 69° HFOV, 55° VFOV
* :ref:`OV9282`

  * NFOV FF (IR/`NoIR <https://www.arducam.com/product/arducam-1mp-ov9282-ccm-drop-in-replacement-for-oak-d/>`__)
  * WFOV FF NoIR (`shop <https://www.arducam.com/product/arducam-1mp-ov9282-fisheye-mono-global-shutter-drop-in-replacement-for-depthai-oak-dnoir/>`__) - 150° DFOV, 127° HFOV, 79.5° VFOV
* :ref:`OV9782`

  * NFOV FF IR (`shop <https://www.arducam.com/product/arducam-1mp-ov9782-color-global-shutter-drop-in-replacement-for-depthai-oak-dnoir-b0352/>`__) - 89.5° DFOV, 80° HFOV, 55° VFOV
* :ref:`OV7251`

  * NFOV FF IR - 86° DFOV, 73° HFOV, 58° VFOV

Arducam short FPC
-----------------

* :ref:`IMX378`

  * PY004 - NFOV, AF, IR filter - 78° DFOV, 66° HFOV, 54° VFOV
  * PY052 - NFOV, FF, IR filter - 81° DFOV, 69° HFOV, 55° VFOV
  * PY060 - WFOV, FF, IR filter - 120° DFOV, 108° HFOV, 93° VFOV
* :ref:`IMX214`

  * PY047 - NFOV, AF, IR filter - 81° DFOV, 69° HFOV, 54° VFOV
  * PY062 - NFOV, FF, IR filter - 81° DFOV, 69° HFOV, 54° VFOV
  * PY072 - NFOV, FF, IR cut filter - 81° DFOV, 69° HFOV, 54° VFOV
  * PY061 - WFOV, FF, IR filter - 117° DFOV, 105° HFOV, 88° VFOV
  * PY138 - WFOV, FF, IR filter, 5cm long connector (used on RAE) - 117° DFOV, 105° HFOV, 88° VFOV
* :ref:`OV9282`

  * PY003 - NFOV, FF, IR filter - 89.5° DFOV, 80° HFOV, 55° VFOV
  * PY044 - NFOV, FF, NoIR filter - 89.5° DFOV, 80° HFOV, 55° VFOV
  * PY091 - NFOV, FF, BandPass @ 940nm - 89.5° DFOV, 80° HFOV, 55° VFOV
  * PY059 - WFOV, FF, IR filter - 150° DFOV, 127° HFOV, 79.5° VFOV
  * PY075 - WFOV, FF, NoIR filter - 150° DFOV, 127° HFOV, 79.5° VFOV
  * PY097 - WFOV, FF, BandPass @ 940nm - 150° DFOV, 127° HFOV, 79.5° VFOV
* :ref:`OV9782`

  * PY074 - NFOV, FF, IR filter - 89.5° DFOV, 80° HFOV, 55° VFOV
  * PY186 - NFOV, FF, BandPass @ 940nm - 89.5° DFOV, 80° HFOV, 55° VFOV
  * PY058 - WFOV, FF, IR filter - 150° DFOV, 127° HFOV, 79.5° VFOV
  * PY139 - WFOV, FF, IR filter, 3.5cm long connector (used on RAE) - 150° DFOV, 127° HFOV, 79.5° VFOV

* :ref:`OV7251`

  * PY013 - NFOV, FF, IR filter - 86° DFOV, 73° HFOV, 55° VFOV
  * PY030 - WFOV, FF, IR filter - 166° DFOV, 163° HFOV, 157° VFOV

* :ref:`IMX582`

  * PY080 - NFOV, AF, IR filter - 71° DFOV, 45° HFOV, 55° VFOV
  * PY101 - NFOV, AF, NoIR filter - 71° DFOV, 45° HFOV, 55° VFOV
  * PY102 - NFOV, FF, BandPass @ 940nm - 71° DFOV, 45° HFOV, 55° VFOV
  * PY106 - NFOV, FF, IR filter - 71° DFOV, 45° HFOV, 55° VFOV
  * PY107 - WFOV, FF, IR filter  - 109° DFOV, 63° HFOV, 89° VFOV
* IMX577

  * PY090 - M12-mount lenses, FF. Default lens: IR filter, LN108 lens

* :ref:`AR0234`

  * PY056 - M12-mount lenses, mechanical focus. Default lens: IR filter, 89.5° DFOV, 80° HFOV, 55° VFOV
  * PY078 - M12-mount lenses, FF, used on :ref:`OAK-D LR`. Default lenses: `M25360H06S <https://www.arducam.com/product/m25360h06s-2/>`__, IR filter

Arducam longer FPC
------------------

* :ref:`AR0234`

  * M12-Mount FF
* :ref:`IMX477`

  * AF (Motorized Focus)
  * M12-Mount FF

.. note::
  M12-mount lenses can easily be replaced in order to fit application needs. Filters (such as BandPass, IR650) are part of the lens, not the camera module.

.. include::  /pages/articles/sensors/includes/low_light_performance.rst

.. include::  /pages/includes/footer-short.rst
