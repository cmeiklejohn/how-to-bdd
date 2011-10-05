!SLIDE center

# Implement #

!SLIDE code

    module Statistics
      module Harvester
        def self.enqueue(node)
          Resque.enqueue(self, node.id)
        end
      end
    end
