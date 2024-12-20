.. _test-config:

***************************************************
Advanced test configurations
***************************************************

.. meta::
    :description: Customize tests run in Splunk Synthetic Monitoring by setting up different devices, variables, locations, test status, and other configurations to best simulate diverse types of traffic to your site or application. 

.. toctree::

   synth-alerts
   built-in-variables
   global-variables
   public-locations
   private-locations
   rum-synth
   try-now
   syn-downtimes

To simulate diverse types of traffic to your site or application, use a range of configuration options to customize each of your tests.

========================================================================================
Devices
========================================================================================

When you set up a test in Splunk Synthetic Monitoring, you can configure the viewport and network connection of the device from which the test is simulated. 

Because Browser tests capture the visual experience of a page, while Uptime and API tests only capture response data, viewport applies to Browser tests only. Network connection applies to all test types. 

----------------------------------------------------------------------------------------
Viewport
----------------------------------------------------------------------------------------
Browser tests in Splunk Synthetic Monitoring capture the visual experience of a user interacting with your application. The viewport is the framed area on a device's screen for viewing information, such as the browser window on a desktop. By default, Browser tests run from a desktop-sized viewport. You can configure tests to run from other viewport sizes to test the user experience from a variety of window sizes and device types. 

When you set up a test, you can choose the viewport size from a list of common devices, or set a custom viewport by height and width. 

----------------------------------------------------------------------------------------
Network connection
----------------------------------------------------------------------------------------
You can run Browser, Uptime, or API tests to simulate network connections of various latencies, including Mobile LTE, Mobile 3G, DSL, Mobile 5G, and cable internet. Testing your site from a variety of connection types lets you monitor the experience of users in a variety of settings. 

========================================================================================
Variables
========================================================================================
Use variables to fill in fields, provide URLs, and enter other information during your tests. 

.. list-table::
   :header-rows: 1
   :widths: 20 80 

   * - :strong:`Variable type`
     - :strong:`Description`
   * - Built-in variables 
     - Built-in variables such as random values, dates and times, or location names, for use in your Browser and API Tests. See :ref:`built-in-variables` to learn more.  
   * - Global variables 
     - Pre-saved, reusable variables you can define once and use across all your Browser and API tests. See :ref:`global-variables` to learn more. 

========================================================================================
Locations
========================================================================================
Specify locations for your tests to simulate traffic from a range of checkpoints around the world, or use private locations to test sites from within a private network.

For more, see: 

* :ref:`public-locations` 
* :ref:`private-locations`

.. * See :ref:`private-locations` to set up private locations. 


========================================================================================
Test state and current status
========================================================================================
You can use the play and pause buttons in the more menu (|more|) of your tests to pause or resume data collection. 

The current status of a test is updated every time you load the :guilabel:`Test Overview` page in Splunk Synthetic Monitoring. The following table describes the possible status types for each test. 

.. list-table::
   :header-rows: 1
   :widths: 20, 80

   * - :strong:`Current status`
     - :strong:`Description`

   * - Pending
     - Splunk Synthetic Monitoring is still retrieving the status of this test. 

   * - Available
     - The test is functioning properly. If the test is active, data is being collected at the set interval and can be viewed in the :guilabel:`Test History` page. If the test is paused, it can be unpaused and will resume collecting data.

   * - No Data 
     - The test isn't currently collecting data. 

   * - Failure
     - The test encountered a failure. 

========================================================================================
Test naming conventions
========================================================================================
Choosing informative names for your tests and alerts helps organize content. Here are some guidelines: 

* Add a category as a prefix to your test name like group, application, brand, or team names so that you can simplify searches. For example, these two Browser tests start with ``[ButtercupGames]``. 

* Add a description about the purpose of the test like the workflow, process, performance, or data source.

.. image:: /_images/synthetics/ButtercupGames-naming-convention.png
      :width: 60%
      :alt: This image shows two Browser tests with the prefix [ButtercupGames].


================================
Troubleshoot broken tests 
================================

See, :ref:`syn-troubleshoot`.



========================================================================================
Filter tests
========================================================================================
You can filter by test type, key-value pairs, and more. 

.. image:: /_images/synthetics/syn-filter-test.png
      :width: 60%
      :alt: This image shows the filter env:prod for all tests on the Synthetic homepage..
