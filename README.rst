My Spark Notes
==================

Quick notes to remember commands and syntax, using pySpark.

Create RDD
------------


.. code-block:: python

   # Create RDD and make 8 partitions from data.
   myRDD = sc.parallelize(data, 8)


