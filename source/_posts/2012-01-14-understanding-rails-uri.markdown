---
layout: post
title: "understanding rails uri"
date: 2012-01-14T02:18:00+05:30
comments: false
categories:
 - rails
 - rails-uri
---
rails-uri module provides us with url manipulation methods

Parse string url
```ruby
url = URI.parse('http://funonrails.com/search/label/rails3')
url.host #=> "http://funonrails.com"
url.port #=> 80
```
URL with Basic Authentication 
```ruby
url = URI.parse('http://sandip:2121@funonrails.com/search/label/rails3')
url.user #=> "sandip"
url.password #=> "2121"
```

Extracting urls form string paragraph
```ruby
URI.extract('http://funonrails.com is rails blog authored by http://sandipransing.github.com contact mailto://sandip@funonrails.com')
#=> ["http://funonrails.com", "http://sandipransing.github.com", "mailto://sandip@funonrails.com"]
```

Split & Join URI
```ruby
URI.split('http://sandip:2121@funonrails.com/search/label/rails3')
#=> ["http", "sandip:2121", "funonrails.com", nil, nil, "/search/label/rails3", nil, nil, nil]

<=> [Scheme, Userinfo, Host, Port, Registry, Path, Opaque, Query, Fragment]
  
URI.join('http://funonrails.com','search/label/rails3')
#=> #<URI::HTTP:0x7fbf9202efc8 URL:http://funonrails.com/search/label/rails3>
```
Escape & Unescape alias encode/decode URI
```ruby
URI.escape('http://funonrails.com/search/?label=\\rails\3')
URI.encode('http://funonrails.com/search/?label=\\rails\3')
#=> "http://funonrails.com/search/?label=%5Crails%5C3"

URI.unescape("http://funonrails.com/search/?label=%5Crails%5C3")
URI.decode("http://funonrails.com/search/?label=%5Crails%5C3")
#=> "http://funonrails.com/search/?label=\\rails\\3"
```

Match urls using regular expressions 
```
"http://funonrails.com/search/label/rails3".sub(URI.regexp(['search'])) do |*matchs|
  p $&
end
#=> "http://funonrails.com/search/label/rails3"
```

Getting requested url inside rails
```ruby
request.request_uri
request.env['REQUEST_URI']
```

Getting previous page url inside rails
```
request.referrer
```
