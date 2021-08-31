require 'bundler/gem_tasks'
require 'rake/testtask'
require 'find'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

# if you run one task very often, you can set it to the default task
desc 'Run tests'
task :default => :test
# this will now run with the command rake and no parameters

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

# List every file in the project
# Exclude those whose names begin with `.`
# Exclude those that are in a directory whose name begins with `.`
desc 'List files'
task :files do
  Find.find(ENV["HOME"] + '/launch_school/todolist_project/') do |path|
    if FileTest.directory?(path)
      Find.prune if File.basename(path).start_with?('.')
      next
    end
    if File.file?(path) && !(File.basename(path).start_with?('.'))
      puts File.basename(path)
    end
  end
end