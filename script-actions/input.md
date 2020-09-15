---
description: Displays an input dialog to the player
---

# Input

## Overview <a id="overview"></a>

There are many cases where we need input from the user, like when you want to know their name.  The Input statement is represented in your Script as an Object and it allows you to define the text to show to your players, the type of input, the default value, validations, etc.

## Properties

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Optional</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Text</td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">The text to be displayed in the input dialog</td>
    </tr>
    <tr>
      <td style="text-align:left">Type</td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">
        <p>The kind of input you want to show.</p>
        <p></p>
        <p>Possible Values:</p>
        <ul>
          <li><code>text</code>
          </li>
          <li><code>password</code>
          </li>
          <li><code>email</code>
          </li>
          <li><code>color</code>
          </li>
          <li><code>select</code>
          </li>
          <li><code>radio</code>
          </li>
          <li><code>checkbox</code>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Default</td>
      <td style="text-align:left"><code>string </code>
      </td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">The default value for the input</td>
    </tr>
    <tr>
      <td style="text-align:left">Options</td>
      <td style="text-align:left"><code>Array&lt;Object&gt;</code>
      </td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">The list of options to present to the player if the input has a type of
        select, radio or checkbox</td>
    </tr>
    <tr>
      <td style="text-align:left">Validation</td>
      <td style="text-align:left"><code>function</code>
      </td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">There are times when you want to validate the user input, to see if it&apos;s
        not empty for example, the Validation property should be a function returning
        a boolean, the validation process is up to what you want. This example
        checks to see if it is empty, but you might put in if trees to disable
        certain names, or something like that.</td>
    </tr>
    <tr>
      <td style="text-align:left">Save</td>
      <td style="text-align:left"><code>function</code>
      </td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">The save function specifies Monogatari will do with the input once it&apos;s
        validated, normally you would save it on storage, but you can do whatever
        you want with it, the save property is then a function that receives the
        input, what you do with it is also up to you.</td>
    </tr>
    <tr>
      <td style="text-align:left">Warning</td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">The message that will be shown in case the input fails the validation,
        something useful for the player to know what you expect from them.</td>
    </tr>
    <tr>
      <td style="text-align:left">actionString</td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Class</td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Timer</td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">A timer configuration object.</td>
    </tr>
  </tbody>
</table>

## Examples







This is a sample script with an input statement:

```javascript
monogatari.script ({
    // The game starts here.
    'Start': [
        'You’ll see an input next',
        {'Input': {
            'Text': 'What is your name?',
            'Validation': function(input) {
                return input.trim ().length > 0;
            },
            'Save': function(input) {
                this.storage().player.name = input;
            },
            'Warning': 'You must enter a name!'
            }
        },

        'Hi {{player.name}}! Welcome to Monogatari!'
    ]
});
```

![The Input panel, displaying its warning after clicking &quot;Ok&quot; without entering in any text.](../.gitbook/assets/image%20%286%29.png)

