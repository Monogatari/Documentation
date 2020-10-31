---
description: Show a notification to the player
---

# Show Notification

## Description

```javascript
'show notification <notification_id> [time]'
```

The `notification` action let's you show a notification to the player. Notifications can be useful for letting them know about a certain event, or even achievement unlock.

**Action ID**: `Notification`

**Reversible**: Yes

**Requires User Interaction**: If no time was provided, the player will need to dismiss the notification but the game will not be interrupted.

## Parameters

| Name | Type | Description |
| :--- | :--- | :--- |
| notification\_id | `string` | The name of the notification you want to show. These must be declared beforehand using this action configuration functions. |
| time | `number` | Optional. The time in **milliseconds** after which the notification will be automatically dismissed. |

## Configuration

To show a notification, you must first declare it with all of it's characteristics. To do so, the notification action has a configuration function where you can define your id or name for each notification and their respective information.

```javascript
Monogatari.action ('Notification').notifications ({
    '<notification_id>': {
        title: '',
        body: '',
        icon: ''
    }
});
```

### Properties

| Name | Type | Description |
| :--- | :--- | :--- |
| title | `string` | The title for the notification |
| body | `string` | The body of the notification |
| icon | `string` | A path to an image that will be shown as the icon for the notification |

## Examples

### Simple Notification

The following script will show a notification that the player will have to manually dismiss.

{% tabs %}
{% tab title="Script" %}
```javascript
Monogatari.script ({
    'Start': [
        'show notification SampleNotification',
        'end'
    ] 
});
```
{% endtab %}

{% tab title="Notification Configuration" %}
```javascript
Monogatari.action ('Notification').notifications ({
    'SampleNotification':{
        title: 'Hey!',
        body: 'This is a notification',
        icon: 'assets/images/notification.png'
    },
});
```
{% endtab %}
{% endtabs %}

### Timed Notification

The following script will make the notification go away automatically after 5 seconds have elapsed. Remember this action receives the time in **milliseconds** so we'll use `5000` to dismiss it after the 5 seconds

{% tabs %}
{% tab title="Script" %}
```javascript
Monogatari.script ({
    'Start': [
        'show notification SampleNotification 5000',
        'end'
    ] 
});
```
{% endtab %}

{% tab title="Notification Configuration" %}
```javascript
Monogatari.action ('Notification').notifications ({
    'SampleNotification':{
        title: 'Hey!',
        body: 'This is a notification',
        icon: 'assets/images/notification.png'
    },
});
```
{% endtab %}
{% endtabs %}

