# DATA-SAGE

Data-Sage is a creative and intriguing app that deals with data analysis and prediction. Here's a breakdown of the meaning:

## Data: 
This part of the name clearly relates to information, statistics, or any kind of data that your app analyzes.

## Sage: 
A "sage" is a person who is known for their wisdom, knowledge, and experience in a particular field. By combining "data" with "sage," the app is intended to be a wise & knowledgeable entity when it comes to handling and interpreting data. The app is a trusted source for data analysis and predictions.

It's important to users seeking data-driven insights. 

## Getting Started:

```
rails new brand-rene -j esbuild -c tailwind -d postgresql -T && cd brand-rene && subl .
```

## Add RSpec:

- In Gemfile, add:
```
group :development, :test do
  gem "debug", platforms: %i[ mri mingw x64_mingw ]
  gem "rspec-rails"
  gem "factory_bot_rails", :require => false
  gem "faker"
  gem "database_cleaner-active_record"
end
```

- In Terminal, Run: 
```
bundle && rails g rspec:install && mkdir spec/support && touch spec/support/factory_bot.rb && touch spec/factories.rb
```

- Configure FactoryBot by adding:
```
# spec/support/factory_bot.rb

require 'factory_bot'

RSpec.configure do |config|
  config.include FactoryBot::Syntax::Methods
  FactoryBot.find_definitions
end
```

- Require support files in rails_helper.rb:
```
require_relative 'support/factory_bot'
```

- In rails_helper.rb, uncomment:
```
Dir[Rails.root.join('spec', 'support', '**', '*.rb')].sort.each { |f| require f }
```

- When User model is generated (or any model) RSpec will generate a factory in factories.rb file. Modify it to look like:

```
# spec/factories.rb

FactoryBot.define do
end
```

- Run Tests with: ```rspec```

