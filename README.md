# qb-inventory

## Future Plans
- Make the inventory fade in/out
- Return the Use, Give & Drop functions in the middle from the old inv

(Any help is appreciated)

## Dependencies
- [qb-core](https://github.com/qbcore-framework/qb-core)
- [qb-smallresources](https://github.com/qbcore-framework/qb-smallresources) - For logging transfer and other history

## Features
- Stashes (Personal and/or Shared)
- Vehicle Trunk & Glovebox
- Weapon Attachments
- Shops
- Item Drops

## Preview
### Shop
![image](https://github.com/MattiVboiii/qb-inventory-edit/assets/57048210/5abef7ff-40e6-4edb-9d66-d8fa7da0f3ca)
### Hotbar
![image](https://cdn.discordapp.com/attachments/1255861184754745354/1270662231520055337/image.png?ex=66b483eb&is=66b3326b&hm=2fcac2bfb87897769ba157de5729fe09fc438f81067b463fbbad6a8126230e4b&)
### Submenu
![image](https://cdn.discordapp.com/attachments/1255861184754745354/1270663135921045636/image.png?ex=66b484c3&is=66b33343&hm=2b3d29b3305e9ab591885cb629fd71b4faeb7c3872dbc0e9bb69999ce601b41f&)

## Changes/Edits
### 27-06-2024
- Added glow and zoom when you hover over an item
- Added the scrollbar back
- Added an entire black transparent background color
- Added nl.lua
- Made the item background color a bit darker
- Made the shop price more bold and bigger

### 06-08-2024
- Added glow in submenu
- Changed to linear transitions
- More color changes

### 07-08-2024
- Changed hotbar label color
- Lifted the hotbar label to reveal durability
- Brightened the radial-gradient in item-slot

## Documentation
https://docs.qbcore.org/qbcore-documentation/qbcore-resources/qb-inventory

## Installation
### Manual
- Download the script and put it in the `[qb]` directory.
- Import `qb-inventory.sql` in your database
- Add the following code to your server.cfg/resouces.cfg

# Migrating from old qb-inventory

## Database
### Upload the new `inventory.sql` file to create the new `inventories` table
### Use the provided `migrate.sql` file to migrate all of your saved inventory data from stashes, trunks, etc
### Once complete, you can delete `gloveboxitems` `stashitems` and `trunkitems` tables from your database
```sql
CREATE TABLE IF NOT EXISTS `inventories` (
  `id` INT(11) NOT NULL AUTO_INCREMENT,
  `identifier` VARCHAR(50) NOT NULL,
  `items` LONGTEXT DEFAULT ('[]'),
  PRIMARY KEY (`identifier`),
  KEY `id` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8mb4;
```

# License

    QBCore Framework
    Copyright (C) 2021 Joshua Eger

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>
