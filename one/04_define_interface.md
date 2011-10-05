!SLIDE center

# Start defining the interface #

!SLIDE code

    When /^the resque scheduler runs the statistics scheduler$/ do
      pending
    end

!SLIDE code

    When /^the resque scheduler runs the statistics scheduler$/ do
      Statistics::Scheduler.perform 
    end
