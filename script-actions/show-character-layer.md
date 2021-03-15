# Show Character Layer

## Description

```
'show character <character_id>:<layer_id> [with [animations] [classes] [properties]]'
```

The character layer action allows you to display or change a layer for a character sprite currently being shown.

**Action ID**: `Show::Character::Layer`

**Reversible**: Yes

**Requires User Interaction**: No

## Examples

Remember every layer and image must be declared in the characters object.

```
'show character e:body normal with fadeIn',
```

The [animation](https://daneden.github.io/animate.css/) is completely optional

```
'show character e:body normal',
'show character e:body normal with fadeIn',
```

### Exit Animations

```text
show character <character_id>:<layer_id> [with [animation] [end-[animation]] [classes]]
```



