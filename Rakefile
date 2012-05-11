# encoding: utf-8

require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
Jeweler::Tasks.new do |gem|
  # gem is a Gem::Specification... see http://docs.rubygems.org/read/chapter/20 for more options
  gem.name = "mongoid_has_arrr"
  gem.homepage = "http://github.com/datenspiel/mongoid_has_arrr"
  gem.license = "MIT"
  gem.summary = %Q{Mongoid <=> ActiveRecord association integration}
  gem.description = %Q{Easily integrate your ActiveRecord models into your Mongoid models}
  gem.email = "dsci@code79.net"
  gem.authors = ["Daniel Schmidt"]
  gem.files = [
    ".document",
    ".rspec",
    "Gemfile",
    "LICENSE.txt",
    "Rakefile",
    "VERSION",
    "spec/spec_helper.rb",
    "lib/mongoid_has_arrr.rb",
    "lib/mongoid/active_record_relations.rb"
  ]
  # dependencies defined in Gemfile
end
Jeweler::RubygemsDotOrgTasks.new

require 'rspec/core'
require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new(:spec) do |spec|
  spec.pattern = FileList['spec/**/*_spec.rb']
end

RSpec::Core::RakeTask.new(:rcov) do |spec|
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

task :default => :spec

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "mongoid_has_arrr #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
