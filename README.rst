My Spark Notes
==================

Quick notes to remember commands and syntax, using pySpark.

Create RDD
------------

Create  a parallelized collection by calling parallelize from SparkContext.

my_RDD is now a Resilient Distributed Datasets (RDD).

.. code-block:: python

   # Create RDD and make 8 partitions from data.
   my_RDD = sc.parallelize(data, 8)

   # Set name
   my_RDD.setName('My test RDD')

   # Show number of partitions
   my_RDD.getNumPartitions()




