# frozen_string_literal: true

require 'bundler/gem_tasks'
require 'rake/testtask'
require 'rdoc/task'
require 'vcr'

README = 'README.rdoc'

Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/test_*.rb'
  test.verbose = false
end

RDoc::Task.new do |rd|
  rd.main = README
  rd.rdoc_files.include(README, 'CHANGELOG.rdoc', 'LICENSE.rdoc', 'lib/**/*.rb')
  rd.rdoc_dir = 'doc'
  rd.title = 'tax_cloud'
end

load 'lib/tasks/tax_cloud.rake'
load 'lib/tasks/tax_codes.rake'
load 'lib/tasks/tax_code_groups.rake'
load 'vcr/tasks/vcr.rake'

require 'rubocop/rake_task'
RuboCop::RakeTask.new(:rubocop)

task default: %i[rubocop test]
