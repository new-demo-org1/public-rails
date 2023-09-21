# frozen_string_literal: true

source "https://rubygems.org"
# if there is a super emergency and rubygems is playing up, try
#source 'http://production.cf.rubygems.org'

gem "bootsnap", require: false, platform: :mri

def rails_master?
  ENV["RAILS_MASTER"] == "1"
end

if rails_master?
  gem "arel", git: "https://github.com/rails/arel.git"
  gem "rails", git: "https://github.com/rails/rails.git"
else
  # NOTE: Until rubygems gives us optional dependencies we are stuck with this needing to be explicit
  # this allows us to include the bits of rails we use without pieces we do not.
  #
  # To issue a rails update bump the version number here
  rails_version = "7.0.7"
  gem "actionmailer", rails_version
  gem "actionpack", rails_version
  gem "actionview", rails_version
  gem "activemodel", rails_version
  gem "activerecord", rails_version
  gem "activesupport", rails_version
  gem "railties", rails_version
  gem "sprockets-rails"
end
