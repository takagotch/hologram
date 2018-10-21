### hologram
---
.rb
https://github.com/trulia/hologram

http://trulia.github.io/hologram/

.py
https://github.com/hologram-io

```
gem 'hologram'
bundle


```

```
source: ./sass
destination: ./docs
documentation_asssets: ./doc_assets
code_example_renderers: ./code_example_renderers
dependencies:
 - ./build
index: basics
nav_level: all
exit_on_warnings: false


/*doc
---
title: Alert
name: alert
category: basics
---
---html_example
  <div class='alert'>Hello</div>
---
*/
  
```

```ruby
require 'coffee-script'
Hologram::CodeExampleRenderer::Factory.define('coffee') do
  example_template 'my_custom_coffee_example_template'
  table_template 'my_custom_coffee_table_template'
  lexer { Rouge::Lexer.find(:coffee) }
  rendered_example do |code|
    CoffeeScript.compile(code)
  end
end

```

```
$('#myDiv').click ->
  alert 'Oh wow we are rendering coffee script'
  
$('#myOtherDiv').click ->
  console.log 'Yeah coffee script!'
$('#yetAnotherDiv').click ->
  window.location =
  

```

```
<script></script>
<div class="codeBlock coffeExample">
  <div class="highlight">
    <pre><%= code_example %></pre>
  </div>
</div>

<div class="codeTable">
  <table>
    <tbody>
      <% examples.each do |example| %>
        <tr>
          <td>
            <script><%= example.rendered_example %></script>
            <div class="codeBlock coffeeExample">
              <div class="highlight">
                <pre><%= example.code_example %></pre>
              </div>
            </div>
        </tr>
      <% end %>
    </tbody>
  </table>
</div>



```

