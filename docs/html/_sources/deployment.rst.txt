Deployment & Upgrades
#####################

Installation Target
===================

+----------------------+---------------------+
| Splunk roles         | required            |
+======================+=====================+
| Search head          |   yes (*)           |
+----------------------+---------------------+
| Monitoring console   |   yes (*)           |
+----------------------+---------------------+
| Indexer tiers        |   no                |
+----------------------+---------------------+

* You can choose to install TrackMe either on your Search Head layer, or on the Splunk Monitoring Console node. (see :ref:`Where to deploy TrackMe?`)
* If you choose to install TrackMe on your Search Head layer in a Search Head Cluster (SHC), Trackme must be deployed through the SHC deployer node.

Dependent Apps
==============

.. hint:: TrackMe has several application dependencies

- Semicircle Donut Chart Viz, Splunk Base: https://splunkbase.splunk.com/app/4378
- Splunk Machine Learning Toolkit, Splunk Base: https://splunkbase.splunk.com/app/2890
- Splunk Timeline - Custom Visualization, Splunk Base: https://splunkbase.splunk.com/app/3120
- Splunk SA CIM - Splunk Common Information Model, Splunk Base: https://splunkbase.splunk.com/app/1621 (require for alert actions and result ingestion purposes)

Indexes
=======

.. hint:: TrackMe requires the creation of an event index and a metric index

- summary event index defaults to ``trackme_summary``, handled by the macro ``trackme_idx``
- metric index defaults to ``trackme_metrics``, handled by the macro ``trackme_metrics_idx``

Customise these macros via the UI or via a local/macros.conf file if you wish to use a different index naming convention.

Installation summary
====================

**The deployment of TrackMe follows Splunk standard practices:**

- Using the application manager in Splunk Web (Settings / Manages apps)

- Extracting the content of the tgz archive in the "apps" directory of Splunk

- For SHC configurations (Search Head Cluster), extract the tgz content in the SHC deployer and publish the SHC bundle

Upgrading
=========

**Upgrading TrackMe relies on Splunk standard application upgrade practices:**

- Using the application manager in Splunk Web for standalone Search Heads or the Monitoring Console node

- Extracting the content of the new tgz archive in the "apps" directory of Splunk

- For SHC configurations (Search Head Cluster), extract the tgz content in the SHC deployer and publish the SHC bundle
