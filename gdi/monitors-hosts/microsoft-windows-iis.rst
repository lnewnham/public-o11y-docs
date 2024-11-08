.. _windows-iis:

Microsoft Windows IIS
=====================

.. meta::
   :description: Use this Splunk Observability Cloud integration for the Windows IIS monitor. See benefits, install, configuration, and metrics

The Splunk Distribution of the OpenTelemetry Collector uses the Smart Agent receiver with the ``windows-iis`` monitor type to report metrics for Windows Internet
Information Services (IIS) and drive the Windows IIS dashboard content.

Windows Performance Counters are the underlying source for these
metrics. Most of the performance counters queried are actually gauges
that represent rates per second and percentages. This integration
reports the instantaneous values for these Windows Performance Counters.
This means that in between a collection interval, spikes could occur on
the Performance Counters. The best way to mitigate this limitation is to
increase the reporting interval on this monitor to collect more
frequently.

This integration is only available on Windows.

Benefits
--------

.. include:: /_includes/benefits.rst

Installation
------------

.. include:: /_includes/collector-installation-windows.rst

Configuration
-------------

.. include:: /_includes/configuration.rst

Example
~~~~~~~

To activate this integration, add the following to your Collector
configuration:

.. code-block:: yaml

   receivers:
     smartagent/windows-iis:
       type: windows-iis
       ...  # Additional config

Next, add the monitor to the ``service.pipelines.metrics.receivers``
section of your configuration file:

.. code-block:: yaml

   service:
     pipelines:
       metrics:
         receivers: [smartagent/windows-iis]

Configuration settings
~~~~~~~~~~~~~~~~~~~~~~

The following table shows the configuration options for the
``windows-iis`` monitor:

.. list-table::
   :widths: 18 18 18 18
   :header-rows: 1

   - 

      - Option
      - Required
      - Type
      - Description
   - 

      - ``counterRefreshInterval``
      - no
      - ``int64``
      - Number of seconds that wildcards in counter paths should be
         expanded and how often to refresh counters from configuration.
         (**default:** ``60s``)
   - 

      - ``printValid``
      - no
      - ``bool``
      - Print out the configurations that match available performance
         counters. This option is used for debugging. (**default:**
         ``false``)

Metrics
-------

The following metrics are available for this integration:

.. raw:: html
 
      <div class="metrics-yaml" url="https://raw.githubusercontent.com/signalfx/splunk-otel-collector/main/internal/signalfx-agent/pkg/monitors/windowsiis/metadata.yaml"></div>

Notes
~~~~~

.. include:: /_includes/metric-defs.rst

Troubleshooting
---------------

.. include:: /_includes/troubleshooting-components.rst
