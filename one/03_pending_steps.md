!SLIDE center

# Pending steps #

!SLIDE code

      When /^the resque scheduler runs the statistics scheduler$/ do
        pending
      end

      Then /^there should be a job to collect stats for the riak node with user "([^"]*)" 
       and ip "([^"]*)" in cluster "([^"]*)"$/ do |user, ip_address, cluster_name|
        pending
      end

!SLIDE code

      Given /^there is a job scheduled to collect stats for the riak node with user "([^"]*)" 
       and ip "([^"]*)" in cluster "([^"]*)"$/ do |user, ip_address, cluster_name|
        pending
      end

      When /^the resque scheduler runs the statistics harvester$/ do
        pending
      end

      Then /^statistics should be gathered for the riak node with user "([^"]*)" 
       and ip "([^"]*)" in cluster "([^"]*)"$/ do |user, ip_address, cluster_name|
        pending
      end
