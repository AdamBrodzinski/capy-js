# capy-js
A Capybara like abstraction for Webdriver.io and ChimpJS


# Example

Clean up your webdriver code with a clean syntax based on Capybara.

```javascript
// As an author
// I want to create a blog post
// So that I can show  my work to the world
feature("Create blog post", () => {
  setup(() => {
    visit('/posts/new')
  })

  scenario("create a blog post", () => {
    fillIn('title', 'Writing tests')
    fillIn('desc', 'How now brown cow')
    clickButton('Create Post')
    
    expect(browser).toHaveContent('How now brown cow')
    expect(browser).toHaveContent('Billy Bob', {within: '.author'})
  })
})
```

#### Works great with CoffeeScript!


```coffeescript
require "cappy-js"
require "cappy-js-underscore" # use an underscore syntax, e.g. fill_in

feature "Create comment", ->
  setup ->
    login_user
    visit "/posts"

  scenario "create a blog post", ->
    fill_in "title", "Writing tests"
    fill_in "desc", "How now brown cow"
    click_button "Create Post"
    expect(browser).to_have_content "How now brown cow"
    expect(browser).to_have_content "Billy Bob", within: ".author"

```
