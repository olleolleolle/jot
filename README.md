# Jot

A light wrapper around the [JWT gem](https://github.com/jwt/ruby-jwt).

## Setup

Configure the gem:

```ruby
Jot.configure do |config|
  config.algorithm = "HS256"
  config.secret = # Something long and complex, such as a value generated by SecureRandom.hex(32)
end
```

## Usage

Encode a payload:

```ruby
JOT.encode({ user_id: 1 }) # => "eyJhbGciOiJIUz..."
```

Decode a payload:

```ruby
JOT.decode("eyJhbGciOiJIUz...") # => { "user_id" => 1 }
```

Exceptions raised for invalid / expired tokens will be the same as those raised by the JWT gem.
