# BriteVerifyApi

The un-official BriteVerifyApi API Client for Ruby

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'brite_verify_api'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install brite_verify_api

## Usage

Create a configuration file and put it in your initializers config/initializers/brite_verify_api.rb

```ruby
BriteVerifyApi.configure do |config|
  config.api_key = "-----Api ----- key -----"
end
```

### Email Verification

```ruby
brite_verify_api = BriteVerifyApi::Clients::Email.new "johndoe@example.com"
brite_verify_api.verify
```

### Testing the integration

Brite charge on per hit basis. On Development Environment you can set up another key in the configure block to prevent that hit (to save money). `default_email_api_reponse` should be hash. It will be returned as it is.

```ruby
BriteVerifyApi.configure do |config|
  config.api_key = "-----Api ----- key -----"
  config.default_email_api_reponse = {
    address: "johndoe@briteverify.com",
    account: "johndoe",
    domain: "briteverify.com",
    status: "valid",
    disposable: false,
    role_address: false,
    duration: 0.104516605
  } if Rails.env.development?
end
```



## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/mohitjain/brite_verify_api. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the BriteVerifyApi project’s codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/mohitjain/brite_verify_api/blob/master/CODE_OF_CONDUCT.md).
