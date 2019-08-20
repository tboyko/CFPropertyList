require 'rubygems'

require 'rubygems/package_task'
require 'rdoc/task'
require 'rake/testtask'
require_relative './gemspec'

desc 'Generate RDoc documentation for the CFPropertyList module.'
Rake::RDocTask.new do |rdoc|
  files = ['README.rdoc', 'LICENSE', 'lib/*.rb', 'lib/**/*.rb']
  rdoc.rdoc_files.add(files)
  rdoc.main = 'README.rdoc'
  rdoc.title = 'CFPropertyList RDoc'
  rdoc.rdoc_dir = 'doc'
  rdoc.options << '--line-numbers' << '--inline-source' << '-c utf8'
end

Gem::PackageTask.new(CFP_PROPERTY_LIST_GEMSPEC) do |pkg|
  pkg.need_tar = true
end

Rake::TestTask.new do |test|
  test.libs << 'test'
  test.test_files = Dir.glob('test/test*.rb')
end

# eof
