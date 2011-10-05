!SLIDE center

# Implement #

!SLIDE code

    module Statistics
      module Scheduler
        def self.perform
          RiakNode.all.each do |node|
            Statistics::Harvester.enqueue(node)
          end
        end
      end
    end

