require 'rake/testtask'
require 'find'
require 'bundler/gem_tasks'

desc 'Say hello'
task :hello do
  puts "Hell over there. This is the `hello` task."
end

desc 'Cheers'
task :cheers do
  puts "Hey, じゃあまたね?!, cheers!"
end

desc 'Fiesta!'
task :fiesta do
  fuego = <<-FIESTA.chomp.gsub(/^\s+/, '')
Fiesta！ Fiesta！　情熱を解き放とう！
Fiesta！ Fiesta！　ワナノマリラ
Te amo！ Te amo！　今ならしたいことしていいわ
Te amo！ Te amo！　早く連れ出して
    FIESTA
    puts fuego
end

desc "Doing it all!"
task :doit => [:hello, :fiesta, :cheers, :test]

desc 'Run tests'
task :default => :test

desc 'Display all files'
task :inventory do
  Find.find('.') do |name|
    next if name.include?('/.')
    puts name if File.file?(name)
  end
end

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end