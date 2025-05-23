.. _activate-builtin-detector:

****************************************************
Part 3: Activate a built-in detector to issue alerts
****************************************************

Now that you have data flowing into Splunk Observability Cloud and you can explore that data using navigators and dashboards, you can set up an alert to help keep you informed about certain conditions in your data.

Create a detector
-----------------

To create an alert, first create a detector that monitors your data for the conditions that you want to be alerted about. When these conditions met, the detector issues an alert.

1. Access the chart you want to create a detector from. This example creates a detector based on the :guilabel:`Memory Used %` chart.
2. Select the :guilabel:`Get Alerts` icon in the upper right of a chart. Some chart data have built-in templates that make it easy for you to create detectors for useful alert conditions. For example, in the :guilabel:`Memory Used %` chart, there is a detector template called :guilabel:`Memory utilization % greater than historical norm`.

   .. image:: /_images/infrastructure/images-k8s-infrastructure-tutorial/k8s-new-detector.png
      :width: 80%
      :alt: A user creates a new detector from a chart.

   This detector sends an alert when memory usage for the last 10 minutes was significantly higher than normal, as compared to the last 24 hours.

3. The :guilabel:`New Detector` panel displays. Select :guilabel:`Add Recipients` to add an email, Splunk Observability Cloud team, or webhook that you want to receive the alert. See :ref:`admin-manage-teams` and :ref:`webhook` to learn more.

   .. image:: /_images/infrastructure/images-k8s-infrastructure-tutorial/k8s-activate-detector.png
      :width: 70%
      :alt: A screen shows a summary of the new detector and alert condition.

4. Select :guilabel:`Activate`. When the data condition is met, Splunk Observability Cloud sends a notification to designated recipients and displays alerts on the Alerts page.

   .. image:: /_images/infrastructure/images-k8s-infrastructure-tutorial/k8s-alert.png
      :width: 70% 
      :alt: An alert that the new detector triggered.

This completes the tutorial. You deployed the Splunk Distribution of the OpenTelemetry Collector on a Kubernetes cluster, viewed your cluster data, and created a detector to issue alerts.

Learn more
----------

* For more details about alerts and detectors, see :ref:`Introduction to alerts and detectors in Splunk Observability Cloud <get-started-detectoralert>`.
* To learn more about the concepts in this tutorial, such as managing dashboards and teams, see :ref:`overview`.