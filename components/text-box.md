# Text-Box

## Properties

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>mode</code>
      </td>
      <td style="text-align:left">
        <p>Default is <code>adv</code>.</p>
        <p></p>
        <p>The mode the textbox is currently displaying dialogs on, whether <code>adv</code> or <code>nvl</code> mode.</p>
      </td>
    </tr>
  </tbody>
</table>

## Methods

### `show (): void`

Shows the text-box element.

### `checkUnread (): void`

This method is called by the [Dialog action ](../script-actions/dialogs.md)after writing an NVL dialog. It will check if the player has an unread dialog \(one that was added and the player has to scroll to read it\). If there is one, the class `unread` will be added to the `text-box` element.

