# Top Level Elements
# Attributes
All top level elements have the same required attributes: name, type, source, and id.<br/>
Attributes are key value pairs with the pattern `key="value"`.<br/>
## Constraints

| Key    | Constraint                                                                                                 |
|--------|------------------------------------------------------------------------------------------------------------|
| name   | any String                                                                                                 |
| type   | any valid [type](#types)                                                                                   |
| source | the name of any [source](#source)                                                                          |
| id     | any string that uniquely identifies this element. A pattern of `ID_AUTHOR_SOURCE_TYPE_NAME` is recommended |

For example the Auril [Deity](#deity):
```xml
<element name="Auril" type="Deity" source="Player’s Handbook" id="ID_WOTC_PHB_DEITY_AURIL">
</element>
```
# Types
## Archetype

## Armor

## Class
Elements of the type class represent character classes.<br/>
For example the Wizard [Class](#class):
```xml
<element name="Wizard" type="Class" source="Player’s Handbook" id="ID_WOTC_PHB_CLASS_WIZARD">
</element>
```
### Nested Elements
Class elements can have nested elements:
- [description](#description) `<description></description>`
- [sheet](#sheet) `<sheet></sheet>`
- [spellcasting](#spellcasting) `<spellcasting></spellcasting>`
- [setters](#setters) `<setters></setters>`
- [rules](#rules) `<rules></rules>`
- [multiclass](#multiclass) `<multiclass></multiclass>`<br/>

#### Constraints
The following elements are **required**:<br>
**_Setters_**<br>
````xml
<setters>
    <set name="hd">die</set>
</setters>
````
With **die** being any valid die.
#### Details
**_Setters_**<br>
A short description of the class:
````xml
<set name="short">A scholarly magic-user capable of manipulating the structures of reality.</set>
````
**_Rules_**<br>
*All Rules are additive and not exclusive*<br/>
Grants ritual casting to the class.
````xml
<grant type="Grants" id="ID_INTERNAL_RITUAL_CASTING" />
````
Grants a [proficiency](#proficiency) to the class, here proficiency with arcane focuses.
````xml
<grant type="Proficiency" id="ID_INTERNAL_PROFICIENCY_SPELLFOCUS_GROUP_ARCANE_FOCUS" />
````
Gives the wizard one `level 1` spell slot at *level 1*.
````xml
<stat name="wizard:spellcasting:slots:1" value="2" level="1" />
````
Specifies the [ability score](#abilityscore) that determines how many spells the Wizard can prepare.
````xml
<stat name="wizard:spellcasting:prepare" value="intelligence:modifier" />
````
Gives the player the option to select three cantrips from the Wizards [spell list](#list) at `level 1`.<br/> For further detail see the Class section in [select](#select).
````xml
<select type="Spell" name="Cantrip (Wizard)" supports="$(spellcasting:list), 0" level="1" number="3" spellcasting="Wizard" />
````
## Class Feature
## Companion
## Companion Action
## Companion Reaction
## Companion Trait
## Feat
## Feat Feature
## Grants
## Item
## Magic Item
## Option
## Proficiency
## Race
## Racial Trait
## Source
## Spell
## Sub Race
## Weapon
## Weapon Category
## Weapon Property