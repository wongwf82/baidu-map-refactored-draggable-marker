# baidu-map-refactored-draggable-marker
Refactored Baidu Map implementation with search box autocomplete. Map is in a Bootstrap modal and pops up when user navigates away from address text field. Markers can be moved by dragging or clicking another point in the map. 

## A few things to note

1. The implementation was in Ruby on Rails. Feel free to extract what you need (esp. the Javascript portion).

2. Baidu map does not seem to have HTTPS version. So you will get **blocked mixed content** error. The solution is:

- Add the following to Gemfile: gem 'rack-ssl-enforcer'
- Run "bundle install"
- Add the following to config/application.rb:
```
    if Rails.env == "production" || Rails.env == "staging"
        config.middleware.use Rack::SslEnforcer, except: [ /edit_venues/ ], strict: true 
    end
```

3. The flow is:

- User moves navigates away from address text field
- The modal pops up
- User enters a location to be searched
- User can click/drag marker
- User clicks Done button
- The city field gets updated
- The next field (Phone) is highlighted

## Creating Baidu Map API Key

1. Install Google Translate Chrome extension (so you can click on "Translate this page" for every page)
2. Visit http://developer.baidu.com/map/
3. Click on API控制台 (or API Console)
4. Create an account and get the key

Happy Mapping!
