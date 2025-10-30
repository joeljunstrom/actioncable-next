# frozen_string_literal: true

require "base64"
require "rake/testtask"
require "pathname"
require "open3"
require "action_cable"

task default: :test

ENV["RAILS_MINITEST_PLUGIN"] = "true"

Rake::TestTask.new do |t|
  t.libs << "test"
  t.test_files = FileList["#{__dir__}/test/**/*_test.rb"]
  t.warning = true
  t.verbose = true
  # TODO: uncomment in rails/rails
  # t.options = "--profile" if ENV["CI"]
  t.ruby_opts = ["--dev"] if defined?(JRUBY_VERSION)
end

namespace :test do
  task isolated: :railties do
    Dir.glob("test/**/*_test.rb").all? do |file|
      sh(Gem.ruby, "-w", "-Ilib:test", file)
    end || raise("Failures")
  end

  task :railties do
    # TODO: uncomment in rails/rails
    # ["action_cable/engine"].all? do |railtie|
    #   sh(Gem.ruby, "-r", railtie, "-e", "'OK'")
    # end || raise("Failures")
  end
end
