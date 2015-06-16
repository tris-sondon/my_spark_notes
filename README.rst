My Spark Notes
==================

Quick notes for commands and syntax, using pySpark.

Create RDD
------------

Create  a parallelized collection by calling parallelize from SparkContext.

my_RDD is now a Resilient Distributed Dataset (RDD).

.. code-block:: python

   # Create RDD and make 8 partitions from data.
   my_RDD = sc.parallelize(data, 8)

   # Set name
   my_RDD.setName('My test RDD')

   # Show number of partitions
   my_RDD.getNumPartitions()

  # Show set of transformations
  my_RDD.toDebugString()

  # define map function 
  rmp = my_RDD.map(lambda x: x**2 + x)

  # collect data
  print rmp.collect()

  rmp = rmp.filter(lambda x: x >  10000)

  print rmp.count()

  print rmp.first()

  print rmp.take(5)

  print rmp.takeOrdered(3)

  print rmp.top(5)

  # reduce 
  print my_RDD.reduce(lambda a, b: a + b)

  print my_RDD.takeSample(withReplacement=True, num=6)

  # takeSample without replacement
  print my_RDD.takeSample(withReplacement=False, num=6)

  print my_RDD.countByValue()

  pp = my_RDD.flatMap(lambda x: (x, x + 's'))

  
  # Cache the RDD
  my_RDD.cache()

  # Is it cached
  print my_RDD.is_cached

  print my_RDD.unpersist()

  # combine all actions

  (sc
    .parallelize(data)
    .map(lambda y: y + 5)
    .filter(lambda x: x < 60)
    .collect())



