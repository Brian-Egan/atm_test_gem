$:.unshift("/Library/RubyMotion/lib")
require 'motion/project/template/ios'
require 'bundler'
require 'bubble-wrap'

$:.unshift("./lib/")
require './lib/atm'

Motion::Project::App.setup do |app|

  unless File.exists?("vendor/Pods/ionicons/ionicons/README.md")
    load "lib/setup/setup.rb"
    File.open("vendor/Pods/ionicons/ionicons/README.md", 'w') {|f| f.write(SetupIon.readme_text)}
  end

end

task :random_task do
  puts "Hello Random Task!"
end


task :spec do
  App.config.spec_mode = true
  spec_files = App.config.spec_files
  App.config.instance_variable_set("@spec_files", spec_files)
  Rake::Task["simulator"].invoke
end