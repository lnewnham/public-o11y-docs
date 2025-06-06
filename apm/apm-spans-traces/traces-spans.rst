.. _apm-traces-spans:

**************************************************************
Manage services, spans, and traces in Splunk APM
**************************************************************

.. meta::
   :description: Learn about traces and spans in Splunk Observability Cloud. Spans are operations, and traces are collections of spans.

.. toctree::
   :hidden:

   service-map
   service-view
   inferred-services
   trace-search
   trace-analyzer
   traces-special-cases
   span-search
   download-traces
   extended-trace-retention
   span-formats
   apm-errors


Spans and traces form the backbone of application monitoring in Splunk APM. Use the following topics to learn about spans and traces and manage your spans and traces effectively, so that you can get the most out of APM full-fidelity tracing: 

* :ref:`apm-service-map`
* :ref:`apm-service-view`
* :ref:`apm-inferred-services`
* :ref:`trace-search`
* :ref:`trace-analyzer`
* :ref:`apm-special-traces`
* :ref:`span-search`
* :ref:`apm-download-traces`
* :ref:`apm-extended-trace-retention`
* :ref:`apm-supported-span-formats`
* :ref:`apm-errors`


.. raw:: html
  
    <embed>
      <h2>What are services?<a name="what-are-services" class="headerlink" href="#what-are-services" title="Permalink to this headline">¶</a></h2>
    </embed>


Services are the key components of the systems you can monitor with Splunk APM. 

.. raw:: html
  
    <embed>
      <h2>What are traces and spans?<a name="what-are-traces-spans" class="headerlink" href="#what-are-traces-spans" title="Permalink to this headline">¶</a></h2>
    </embed>


A trace is a collection of operations that represents a unique transaction handled by an application and its constituent services. A span represents a single operation within a trace. 

Splunk APM collects incoming spans into traces and analyzes them to give you full fidelity access to your application data. After all spans of a trace are ingested and analyzed, the trace is available to view in all parts of APM.

The following image illustrates the relationship between traces and spans:  

.. image:: /_images/apm/terms-concepts/traces-spans.png
   :width: 70%
   :alt: This image shows a trace represented by a series of multicolored bars labeled with the letters A, B, C, D, and E. Each lettered bar represents a single span. The spans are organized to visually represent a hierarchical relationship in which span A is the parent span and the subsequent spans are its children.

A span might refer to another span as its parent, indicating a relationship between operations involved in the trace. In the preceding image, span A is a parent span, and span B is a child span. This relationship might indicate that, for example, span A makes a service call that triggers the operation captured by span B. In this image, span C is also a child of span B, and so on. 

.. raw:: html
  
    <embed>
      <h2>Span metadata<a name="span-metadata" class="headerlink" href="#span-metadata" title="Permalink to this headline">¶</a></h2>
    </embed>

Each span contains metadata about the operation captured by the span and the service in which the operation took place. 

Span metadata includes a set of basic metadata including information such as the service and operation. Spans also include span tags, which provide additional operation-specific metadata. See the Span tags section in this topic to learn more. 

Each span contains the following basic metadata: 

.. list-table::
   :header-rows: 1
   :widths: 20, 40, 40

   * - :strong:`Span tag key`
     - :strong:`Example value`
     - :strong:`Description`

   * - Service
     - ``checkoutservice``
     - Name of the service associated with the span

   * - Operation
     - ``cart/checkout``
     -  Name of the operation that the span represents
 
   * - Span ID
     - ``976gh68e482k8s0m``
     -  Unique 16-character identifier for the specific span
     
   * - Parent ID (if applicable)
     - ``756e643so999cl4``
     -  Unique 16-character identifier for the span's parent span, if it has one

   * - Time (Start - End)
     - ``2022-01-05T11:51:56.360229 - 2022-01-05T11:51:56.932772``
     -  Starting and ending timestamps for the span
 
   * - Duration
     - ``573ms``
     -  Duration of the span (in seconds, milliseconds, or microseconds) 

   * - Relative Start
     - ``+972µs``
     -  Delay between the start of the parent trace and the start of this particular span


.. raw:: html
  
    <embed>
      <h2>Span tags<a name="span-tags" class="headerlink" href="#span-tags" title="Permalink to this headline">¶</a></h2>
    </embed>


Span tags are key-value pairs that provide additional information and context about the operations a span represents. Both the keys and values are strings, and span tag keys for a single span must be unique. You can use span tags to query and filter traces, or to get information about the spans of a trace during troubleshooting.

You can add custom span tags through the OpenTelemetry Collector, or when you instrument an application. For more information about using span tags to analyze service performance, see :ref:`apm-span-tags`. 

Span tags are most useful when they follow a simple, dependable system of naming conventions. See :ref:`span-tag-naming` to learn about OpenTelemetry naming conventions for span tags. 

.. note:: Span tags in Splunk APM are distinct from metadata tags in Splunk Infrastructure Monitoring, which are searchable labels or keywords you can assign to metric dimensions in the form of strings rather than as key-value pairs. To learn more about metadata tags, see :ref:`metadata-infra-tags`.