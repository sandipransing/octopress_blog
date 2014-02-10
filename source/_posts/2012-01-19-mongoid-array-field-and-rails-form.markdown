---
layout: post
title: "mongoid array field and rails form"
date: 2012-01-19T23:59:00+05:30
comments: false
categories:
 - mongoid
 - rails 3
---
Mongoid document supports array as field. array field in mongoid document is a ruby array but its quite complex to manage array field in rails forms.

After lot of google and reading comments from stack-overflow at last i felt helpless. Finally after doing research on rails form helper object(form_for, fields_for) am pleased to get it working as expected :)

In below example, product can have multiple categories
```ruby
class Product
  CATEGORIES = %w(Apparel Media Software Sports Agri Education)
  include Mongoid::Document
  field :name, :type => String
  field :categories, :type => Array
end
```
Here is form code 
```haml
= form_for(@product) do |f|
  = f.text_field :name
  - Product::CATEGORIES.each do |category|
    = f.check_box :categories, :name => "product[categories][]", category
```

Here is products controller code
```ruby
class ProductsController < ApplicationController
  before_filter :load_product, :only => [:new, :create]
  
  [...]
  
  # We don't need new action to be defined
  
  def create
    @product.attributes = params[:product]
    # Here we need to reject blank categories
    @product.categories.reject!(&:blank?)
    if @product.save
      flash[:notice] = I18n.t('product.create.success')
      redirect_to(:action => :index)
    else
      render :action => :new
    end
  end
  
  [...]
  
  private
  def load_product
    @product = Product.new
  end
end
```
