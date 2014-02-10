---
layout: post
title: "dynamic & bounded parameters and named routes"
date: 2012-01-31T02:43:00+05:30
comments: false
categories:
 - rails 3
 - routes
---

<div class='post'>
Rails routes can be customized as your own routes with parameters but first you should understand how routes behaves. <br/> <b>Adding dynamic parameters to routes </b> <br/>Here exact parameters are matched to route and presence of each parameter is mandatory in order to construct urls. blank parameter will raise RoutingError exception. <br/>Exact matched named route declared as -  <pre class=ruby>  match ':a/:b/:c', :to => 'home#index', :as => :q </pre> now go to the rails console - <pre class=ruby> ruby-1.9.3-head :005 > app.q_url(:a, :b, :c)   => "http://www.example.com/a/b/c"        ruby-1.9.3-head :006 > app.q_url(:a, :b, '')   ActionController::RoutingError: No route matches {:controller=>"home", :a=>:a, :b=>:b, :c=>""} </pre><b>Bound parameters to named routes</b><br/>If you are too sure that certain parameter can be blank then you can define it as optional parameter inside route -  <br/><pre class=ruby> match ':a/:b(/:c)', :to => 'home#index', :as => :q </pre><b>rails console</b><pre class=ruby> ruby-1.9.3-head :010 > app.q_url(:a, :b, '')   => "http://www.example.com/a/b?c="   ruby-1.9.3-head :011 > app.q_url(:a, :b)   => "http://www.example.com/a/b" </pre></div>
