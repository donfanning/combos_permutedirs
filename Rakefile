require 'rubygems'
require 'rake'

begin
  gem 'rubygems-tasks', '>= 0.2.4'
  require 'rubygems/tasks'

  Gem::Tasks.new
rescue LoadError => e
  warn e.message
  warn "Run `gem install rubygems-tasks` to install 'rubygems/tasks'."
end

begin
  gem 'rspec', '>= 3.3.0'
  require 'rspec/core/rake_task'

  RSpec::Core::RakeTask.new
rescue LoadError => e
  task :spec do
    abort "Please run `gem install rspec` to install RSpec."
  end
end

task :test => :spec
task :default => :spec

begin
  gem 'yard'
  require 'yard'

  YARD::Rake::YardocTask.new  
rescue LoadError => e
  task :yard do
    abort "Please run `gem install yard` to install YARD."
  end
end

task :benchmark do
  Dir.glob('benchmarks/*.rb') { |script| ruby(script) }
end