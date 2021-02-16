source 'https://rubygems.org'

gemspec

group :guard do
  gem 'coolline'
  gem 'guard'
  gem 'guard-cucumber'
  gem 'guard-rspec'
  gem 'guard-spork'

  require 'rbconfig'

  if RbConfig::CONFIG['target_os'] =~ /darwin/i
    gem 'growl', require: false
    gem 'rb-fsevent', require: false

    if `uname`.strip == 'Darwin' && `sw_vers -productVersion`.strip >= '10.8'
      gem 'terminal-notifier-guard', '~> 1.5.3', require: false
    end rescue Errno::ENOENT

  elsif RbConfig::CONFIG['target_os'] =~ /linux/i
    gem 'libnotify',  '~> 0.8.0', require: false
    gem 'rb-inotify', require: false

  elsif RbConfig::CONFIG['target_os'] =~ /mswin|mingw/i
    gem 'rb-notifu', '>= 0.0.4', require: false
    gem 'wdm', require: false
    gem 'win32console', require: false
  end
end

group :test do
  gem "berkshelf-api"
  gem "reel"
end

gem 'ridley',
    git: 'https://github.com/mes/ridley.git',
    branch: 'update-faraday'
