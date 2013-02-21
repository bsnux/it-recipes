Ruby objects and classes
------------------------

This is a simple example for understanding how classes and objects
work in Ruby:

    class Test
      @@class_vble = 1
      attr_accessor :setter_getter_attr
      attr_reader :reader_attr
      attr_writer :writer_attr

      def initialize(param1, param2)
        @instance_vble_p1 = param1
        @instance_vble_p2 = param2

        @setter_getter_attr = 'attr_accessor'
        @reader_attr = 'reader'
        @writer_attr = 'writer'
      end

      def hello
        puts "Hello!!"
      end

      def get_val1
        puts @instance_vble_p1
      end

      def get_writer
        puts @writer_attr
      end

      def get_cl_vble
        @@class_vble += 1
        puts @@class_vble
      end

      private

      def first_private
        puts "I'm private!"
      end

      protected

      def first_protected
        puts "I'm protected!"
      end
    end

    class AnotherTest < Test
      def another_method
        puts "I belog to AnotherTest"
      end
    end

    if __FILE__ == $0
      t = Test.new('a', 'b')

      t.hello

      t.get_val1

      puts t.setter_getter_attr
      t.setter_getter_attr = 'Changed!'
      puts t.setter_getter_attr

      puts t.reader_attr

      t.writer_attr = 'Changed!'
      t.get_writer

      t.get_cl_vble

      n = Test.new('c', 'd')
      n.get_cl_vble

      x = AnotherTest.new('e', 'f')
      x.hello
      x.get_val1
      x.get_cl_vble

    end
