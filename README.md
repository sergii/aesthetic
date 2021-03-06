# Aesthetic

[![Build Status](https://travis-ci.org/benpickles/aesthetic.svg?branch=master)](https://travis-ci.org/benpickles/aesthetic)

Aesthetic is a tool to help you regression-test your site's aesthetic and ensure that tiny CSS changes don't have unintentional side effects in other areas of your site. Aesthetic helps you identify visual changes throughout your site to give you the confidence to freely refactor your CSS from the ground up instead of building up layers of hacks that you'll find time to fix one day.

## Usage

```ruby
aesthetic do
  # A screenshot is taken for each breakpoint.
  breakpoint :tablet, 768
  breakpoint :desktop, 1024

  # The `screenshot` method visits a URL and saves a screenshot.
  screenshot :homepage, 'http://example.com'

  # You can utilise the full Capybara DSL in example blocks.
  example 'My Account' do
    visit 'http://example.com'
    click_link 'My Account'

    # Use the `screenshot` method to save a screenshot.
    screenshot :my_account
  end
end
```
