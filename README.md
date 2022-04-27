# datafusion_cdap_spark_compute_plugin
Complete example project to create a custom Google cloud datafusion (CDAP) spark compute plugin. Sourced and adapted from the documentation where there is no quickstart project.

# Spark Compute Plugin

A SparkCompute plugin is used to transform a collection of input records into a collection of output records. It can be used in both batch and real-time data pipelines. It is similar to a Transform, except instead of transforming its input record by record, it transforms an entire collection. In a SparkCompute plugin, you are given access to anything you would be able to do in a Spark program.

In order to implement a Spark Compute Plugin, you extend the SparkCompute class.

## Methods
### configurePipeline():
Used to perform any validation on the application configuration that is required by this plugin or to create any datasets if the fieldName for a dataset is not a macro.
### transform():
This method is given a Spark RDD (Resilient Distributed Dataset) containing every object that is received from the previous stage. This method then performs Spark operations on the input to transform it into an output RDD that will be sent to the next stage.