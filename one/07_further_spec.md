!SLIDE center

# Spec the harvester #

!SLIDE code

    describe Statistics::Harvester do 
      let(:riak_node) do
        RiakNode.new.tap do |node|
          node.stub(:id).and_return(1)
        end
      end
    end

!SLIDE code

    describe Statistics::Harvester do 
      let(:riak_node) do
        RiakNode.new.tap do |node|
          node.stub(:id).and_return(1)
        end
      end

      it "should know how to enqueue a harvester job" do 
        Resque.should_receive(:enqueue).with(subject, 1).and_return(true)
        subject.enqueue(riak_node)
      end
    end
