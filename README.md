# Sms24x7

Sending SMS via sms24x7 API. For more details see http://sms24x7.ru/api/

## Installation

Add this line to your application's Gemfile:

    gem 'sms24x7'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install sms24x7

## Usage

In the begining, you need to [register](http://outbox.sms24x7.ru/registration.php?pattern_id=2) for sending SMS through sms24x7 gateway.

There are two ways for sending your SMS.

The first - it's sending a SMS to one recipient. To do this, use:

```
SmsApi.push_msg_nologin('your@email.com', 'your_password', 'recipient_phone', 'sms_text', params)
```

here `recipient_phone` - is a phone number in format '7xxxyyyzzzz' and `params` - additional params that you can see in [documentation](http://sms24x7.ru/wp-content/uploads/2011/04/api_manual.pdf).

The second way - it's sending multiple SMS to multiple recipients.

```
SmsApi.login('your@email.com', 'your_password')
recipient_phones_str_arr.each do |recipient_phone|
  SmsApi.push_msg(recipient_phone, 'sms_text', params)
end
```

here `recipient_phones_str_arr` - it's array that consist phone numbers as strings in format that represented above.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
