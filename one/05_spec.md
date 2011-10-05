!SLIDE center

# Write the spec #

!SLIDE code

    describe Statistics::Scheduler do 
      let(:riak_node) { RiakNode.new }
    end

!SLIDE code

    describe Statistics::Scheduler do 
      let(:riak_node) { RiakNode.new }

      it "should schedule jobs to collect stats for all riak nodes" do 
        RiakNode.stub(:all).and_return([riak_node])
        Statistics::Harvester.should_receive(:enqueue).with(riak_node).and_return(true)
        subject.perform 
      end
    end
