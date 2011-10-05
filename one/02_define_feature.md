!SLIDE center

# Define the feature #

!SLIDE code

    Feature: Scheduled jobs

      In order to effectively use the Overriak service
      As a registered user with riak nodes and clusters
      My nodes should have scheduled jobs created for them

      Background:
        Given there is a riak cluster named "Test Cluster" 
         that belongs to "user@domain.com"
        And there is a riak node with user "riak" 
         and ip "127.0.0.1" in cluster "Test Cluster"

!SLIDE code

      Scenario: Job is scheduled to collect stats every minute
        When the resque scheduler runs the statistics scheduler
        Then there should be a job to collect stats for the riak node 
         with user "riak" and ip "127.0.0.1" in cluster "Test Cluster"

      Scenario: Job is run to collect stats for a particular riak node
        Given there is a job scheduled to collect stats for the riak node 
         with user "riak" and ip "127.0.0.1" in cluster "Test Cluster"
        When the resque scheduler runs the statistics harvester
        Then statistics should be gathered for the riak node 
         with user "riak" and ip "127.0.0.1" in cluster "Test Cluster"
