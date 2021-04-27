require "rake/testtask"
require 'find'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

desc 'List files'
task :list do
  list = []
  Find.find('.') do |path|
    list << path unless path.include?('/.') || !File.file?(path)
  end
  puts list
end

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

