.. _operative_temperature_range:

Operative temperature range
===========================

VPU temperature range
*********************

The :ref:`RVC2` is rated for industrial use and has operating temperature of -40°C to 105°C,
while other components have a higher temperature range.

General use case
****************

Max temperature
---------------

In the general use case at a 25°C ambient, the chip running at full power (i.e. worst-case heat generation) resides at around 70°C maximum,
which sets the thermal margin to a minimum of 35°C.

Since devices generate about 45°C in worst-case, this means the **maximum ambient temperature** should *theoretically* be **60°C**
(:code:`105°C-45°C=60°C`).


OAK-D-Lite max temperature
--------------------------

As we wanted to make :ref:`OAK-D-Lite` as small as possible, we had to use a smaller heatsink. This means the maximum ambient temperature is about 40°C.

.. list-table::
   :header-rows: 1

   * - Test
     - Ambient [°C]
     - VPU [°C]
     - HS-CPU [°C]
     - HS [°C]
   * - :ref:`Test 1`
     - 30
     - 87
     - 71.5
     - 67
   * - :ref:`Test 2`
     - 35
     - 94
     - 77
     - 73
   * - :ref:`Test 3`
     - 40
     - 100
     - 88
     - 78
   * - :ref:`Test 4`
     - 50
     - /
     - /
     - /
   * - :ref:`Test 5`
     - 50
     - 112
     - 95
     - 90

Legend:

- ``Ambient`` temperature means the temperature of the air around the device
- ``VPU`` is the temperature of the :ref:`RVC2` (as reported by depthai)
- ``HS-CPU`` is the temperature of the enclosure where VPU is located
- ``HS`` is the temperature of the enclosure on the opposite side of the VPU

Tests 1-4 were running all 3 cameras at 30FPS, stereo depth, NN (mobilenet), and video encoding, so the maximum workload possible.
As test 4 resulted in a crash of the device (at 125°C VPU temperature), test 5 was done without video encoding (only NN, stereo depth, and 3 cameras at 30FPS).

Min temperature
---------------

While the :ref:`RVC2 <RVC2>` SoC has the lowest operating temperature of -40°C, we have only tested our devices at the lowest ambient temperature of
-25.1°C and they worked as expected. Minimum temperature would depend on the computational workload, as the VPU would generate more heat
when running at full power, which would heat up the device.

Note that **Pro versions** (:ref:`OAK-D Pro`, :ref:`OAK-D Pro PoE`) have on-board IR laser dot projector that has an operating temperature range
of 10°C - 60°C (absolute limit 0°C - 80°C). If you would like to use Pro devices below 0°C, we would suggest running the
device (without projector) for a few minutes so the device heats up, which would also heat up the laser projector, hopefully
above 10°C.

CCM heating
***********

CCM (Compact Camera Module) are the modules that are integrated into the OAK cameras. OAK-D has 3 CCMs, 2x for stereo pair, and in the middle is the RGB camera.
CCMs themselves have different operating ranges and also some have lower thermal noise than others (eg. on OAK Lite cameras, those CCMs have worse thermal noise).

.. thumbnail:: https://github.com/luxonis/depthai-hardware/assets/18037362/cb3de541-1251-454e-82ed-2cd1a4fcc29d

We have done some quick testing on CCM heating with different sensors; :ref:`IMX582`, :ref:`IMX214`, :ref:`OV9282`, :ref:`IMX378`.


.. list-table::
   :header-rows: 1

   * - Sensor
     - Max temp [°C]
     - Temp diff [°C]
   * - :ref:`IMX582`
     - 64°C
     - 30°C
   * - :ref:`IMX214`
     - 62°C
     - 29°C
   * - :ref:`OV9282`
     - 50°C
     - 13°C
   * - :ref:`IMX378`
     - 46°C
     - 12°C

*Temp diff* is the difference between the ambient temperature and the temperature of the CCM.

.. thumbnail:: https://github.com/luxonis/depthai-hardware/assets/18037362/9a40c831-54ff-4fe5-9368-520062919283

.. thumbnail:: https://github.com/luxonis/depthai-hardware/assets/18037362/68420ffa-cfcd-449c-bf67-454ba1c0bc43


Command used for testing
************************

We have tested thermals of our devices with max load, and you can achieve that by using the depthai_demo:
:code:`python3 depthai_demo.py -sub -lrc -rgbr 2160 --report cpu -enc color -encout /dev/null`

This command has the maximum power consumption, therefore the devices have the highest heat output.

Note the framerate of the RGB camera is set to 30 (:code:`-rgbf 30`). If it would be set any higher, it would be bottlenecked
by the neural network.

Results of our tests
********************

All devices were tested in an ambient temperature of 18°C to 20°C.

Test on the `OAK-D-PCBA <https://docs.luxonis.com/projects/hardware/en/latest/pages/BW1098OAK.html#oak-d-pcba>`__ - rear thermal plate with black anodizing and Laird HD320 TIM:

* Heatsink max temperature: 43°C
* Die max temperature: 60°C

.. thumbnail:: /_static/images/temperature_range/OAK-D-PCBA_heatsink.jpeg

Test on the megaAI with the Tianmai 6.5W/K TIM for both the front heatsink and the MX. TMA-6518 (0.5mm) for the MX and the TMA-6500 (2mm) 
for the front were used. This test was with the BW machined heatsink.

* Heatsink max temperature: 61°C
* Die max temperature: 73°C

.. thumbnail:: /_static/images/temperature_range/megaAI_heatsink.jpeg

Tests for OAK-1:

1. 6535 back TIM only:

* Die max temperature: 78°C
* Rear heatsink max temperature: 62°C
* Front heatsink max temperature: 60°C

2. 6510 front + 6535 back TIM:

* Die max temperature: 70°C
* Rear heatsink max temperature: 59°C
* Front heatsink max temperature: 60°C


Test with T1 OAK-1 sample:

* Rear heatsink max temperature: 61°C
* Front heatsink max temperature: 63°C
* Die max temperature: 73°C

.. thumbnail:: /_static/images/temperature_range/OAK-1_heatsink.jpeg

.. toctree::
   :maxdepth: 1
   :hidden:

   lite_temp_test.rst

.. include::  /pages/includes/footer-short.rst