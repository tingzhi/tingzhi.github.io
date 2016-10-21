# Arch Linux Installation Walkthrough

## Environment

### 1 VM on Proxmox VE

- 2 cores CPU

- 512M RAM

- 10GB HD


## Instructions

### Verify the boot mode

```
# ls /sys/firmware/efi/efivars
```

### Check Internet connection

```
# ping archlinux.org
```

### Update the system clock

```
# timedatectl set-ntp true
```

#### Adjust the time zone to Pacific

```
# timedatectl list-timezones
# timedatectl set-timezone America/Los_Angelos
```

### Partition the disks

#### List the devices

```
# fdisk -l 
```

#### Partition

```
# fdisk /dev/sda
```

Inside fdisk prompt, the commands are the following:

- **p** print the partition table
- **n** create a new partition

- **d** delete a partition

- **q** quit without saving changes

- **w** write the new partition table and exit


Just follow the instructions and I made one partition for the root directory.

#### Format the partition

```
# mkfs.ext4 /dev/sda1
```

#### Mount the file systems

```
# mount /dev/sda1 /mnt
```

### Install the base packages

```
# pacstrap /mnt base
```

### Configure the system

#### Fstab & Chroot

```
# genfstab -U /mnt >> /mnt/etc/fstab
# arch-chroot /mnt
```

### Time zone

#### Set the time zone:

```
# ln -s /usr/share/zoneinfo/Region/City /etc/localtime
```

### Locale

```
# locale-gen
# nano /etc/locale.conf
LANG=en_US.UTF-8
```

### Hostname

```
# nano /etc/hostname
coolarch
# nano /etc/hosts
127.0.0.1	coolarch.localdomain	coolarch
```

### Set root password

```
# passwd
```

### Boot loader

I chose GRUB (GRand Unified Bootloader)

```
# pacman -S grub
# grub-install --target=i386-pc /dev/sda
# grub-mkconfig -o /boot/grub/grub.cfg
```

### Reboot

Exit the chroot environment, unmount all the partitions, and restart the computer.

```
# exit
# umount -R /mnt
# reboot
```

------

After restart the machine, you should be able to login into the new system with the root account.



## Reference

[Arch Linux Installation Guide](https://wiki.archlinux.org/index.php/Installation_guide#Update_the_system_clock)

[fdisk](http://www.tldp.org/HOWTO/Partition/fdisk_partitioning.html)



I dislike this kind of condition expression. It's not explicit and it takes time for others to understand.

```python
while not name:
    print('Enter your name:')
    name = raw_input()
```

```python
if numOfGuests:
    print('Be sure to have enrough room for all your guests.')
```

I would rather write the second example like this:

```python
if numOfGuests > 0:
    print('Be sure to have enrough room for all your guests.')
```

It is more explicit what I am trying to do. Sure, number of guests would never be negative. So the obvious posibilities would be 0 (False) or greater than 0 (True). But why not just write like that. It's just more clearer.



# Software and Apps Essential to Thesis Writing on Mac

#### TexStudio

Perfect for LaTex editing. LaTex has great support for math equations and is greatly used in science and engineering field.

#### Overleaf

#### ShareLaTex

#### Grammarly

Free grammar checker

#### Google Drive, Dropbox, Github

Back up your thesis, simulation code, and simulation data.

#### Keynote

Presentation

#### Mendeley

A free reference manager.

#### Zotero

A powerful, easy-to-use research tool that helps you gather, organize, and analyze sources.

#### Writefull

It is an app that provides feedback on your writing by checking your text against databases of correct language.

## Programming Language needed

Python

C++

Bash script

R



# Essentials for Job Hunting

ResumeUp

LinkedIn

Github

Personal website

A good email address

Cover letter

Resume

# Data Process Workflow

## Getting average, minimum, maximum, standard deviation



# Summary of Hear the Wind Sing

## Type of fabric

gingham

terry-cloth

Calico

seersucker





## Type of flower

azaleas

## Type of plant

wicker

rattan





You will only save 12 minutes when you drive from Corvallis to Portland and increase speed from 65 mph to 75 mph.



# 5 Ways to Overcome Decision Fatigue

[Reference from this post](http://jamesclear.com/willpower-decision-fatigue)

| Advice                                   | Summary                                  |
| ---------------------------------------- | ---------------------------------------- |
| Plan daily decisions the night before    | Automate decisions that we make over and over and over again. |
| Do the most imporant thing first         | Put your best energy towards it.         |
| Stop making decisions. Start making commitments. | Schedule important things rather than hoping making the right choice each day. |
| If you have to make good decisions later in the day, then eat somedthing first. |                                          |
| Simplify.                                | Eliminate something if it isn't important to you. Simply reduce the number of inputs will improve the output. |



Describe the sensation after eating wasabi



One wok for quick stir-fry and one wok for braising dish. When blench meat or vegetables, use a decidated pot.



Cast iron skillet is used for making 

- steak 
- corn bread



# Dishes We Like

## Meat dish

### Chicken

卤鸡腿

三杯鸡

酱油鸡翅

红烧鸡翅

咖喱鸡

口蘑烧鸡块

chicken adobo

### Pork

红烧肉

板栗红烧肉

糖醋排骨

红烧狮子头

蜜汁叉烧

香菇烧肉

肉末炖蛋

### Beef

红烧牛腩

精炖牛尾汤

五香酱牛肉

Slow cooked beef shank

### Other

Garlic king prawns and sherry

## Quick Stir-fry dish

### With Meat

豇豆炒肉末

青椒肉丝

宫保鸡丁

虾仁炒蛋

香菇炒肉片

### Without Meat

地三鲜

青椒土豆丝

黄瓜炒鸡蛋

板栗烧双菇

番茄炒蛋

Garlic Lettuce

Garlic Spinach

清炒小白菜

## Soup

白萝卜排骨汤

番茄蛋花汤

## Stew

Gumbo

beef stew

## Noodle Dish

红烧牛肉面

Pho ramen

One pan pasta

炸酱面

## Other

馄饨

茶叶蛋

葱油饼

牛排沙拉

蛋炒饭

水饺

小米粥



## Material I need to pay attention to

香菇
腐竹
木耳



# Stir-fried Eggs and Tomatoes

## Prep work

Rinse vegetables

Dry vegetables

Cut tomatoes

Finely chop scallion

Beat eggs

Make cornstarch slurry

Grab ketchup, salt, sugar, vegetable oil

Grab measure spoons, a big plate, a wok, and a skillet.

Make sure you have everything you need before start cooking because once you start cooking everything goes very fast and you will not have time to search for stuff you need.

## Why do we need to make sure vegetables are as dry as possible?

Rinse the vegetables and let them air dry if you have time. If you are in rush, make sure to dry the vegetables using paper towel. 

During chopping, clean the cutting board and knife with paper towel NOT water.

The reason that I emphsis this is that (a) stir-fry usually happen in a hot wok with oil in it. Residual water on the vegetables will cause the oil to splatter (b) introduce water into the wok will lower the temperature and the vegetables will get steamed instead of stir-fry.

## Why do we cut the tomato into cubes?

Dice would be too small and result in a tomato sauce. Big chunks would not accomodate quick stir-fry technique.

## How to cut the tomato into cubes?

Cut the tomato in half. On each half, one cut horizontal, and three or four vertical cuts. Total of 8 or 10 cuts.

## How to beat the eggs?

Two eggs cracked into a bowl, not a cup because cup will not give you the room to do proper beaten action. Use a pair of chopsticks or a fork, tilt the bowl about 15 degrees, and beat the eggs with a circular motion for about 1 minute. The end result should have a consistant color, not blotchy white and yellow preferreably some small foam would form on the surface.

## How to finely chop scallion?

See a youtube video about how to use a knife.

Two counterintuitive facts about knife

1. A sharp knife is a safe knife.
2. Use left hand middle finger knuckle to guide the knife is safer than not doing so (out of fear that the knife will cut your finger).

Cut the scallion into 2 or 3 equal length parts and align them together and start fine chopping.

Use left hand's middle finger knuckle to guide the knife, move slowly to the left. As the knuckle move, the knife follows.

## Why do we need to use a wok and a skillet?

A well seasoned carbon steel wok actually will not introduce metalic taste into this dish. But since our wok is not well seasoned, I think it's better not to cook tomato in that wok.

That being said, we could cook the egg in the skillet too but I like to cook eggs in a wok because of its shape that allow the eggs to be concentrated in a small area instead of spread in a big flat surface. I like the egg curds to have a bit volume, not a flat sheet of egg.

For cooking the tomato and combining eggs into tomato, I like to use skillet because it has a large flat surface. The large surface allows the tomato to quickly sweat down. Using a pot to cook tomato will likely cause a steamed tomato sauce rather than a stir-fried tomato.

That being said, if you are fine with flat egg curds, you could cook the whole dish in just a skillet. Or if you have a stainless steel or non-stick wok, you could cook this dish in just one wok too (This is an ideal case).

## Why do we cook the eggs first?

Some people cook tomatoes first. But that means you need to clean the pan half way after you set aside tomatos in a plate. The reason is that the residual cornstarch slurry will be very sticky after heating. To cook eggs in a sticky pan is not a good idea.

So if we choose to cook tomatoes first, we will need to clean the pan twice. One in the middle of cooking, and one after cooking.

However, if we choose to cook eggs first, the cornstarch slurry will be added in the end. So we don't need to clean the pan in the middle.

## Why do we stir in the cornstarch slurry?

Cornstarch slurry is used to quickly thicken the sauce. It is totally optional. 



# 豇豆炒肉末

## Ingredients

1/2 tsp sugar

1 tsp light soy sauce

1 tsp cornstarch

1 tsp + 1tbsp + 1tbsp vegetable oil

200g ground pork

200g long beans

1/2 tsp salt

25g black beans (1-1/2 tbsp ?)

1 + 2 cloves garlic smashed

1/3 cup water

## Instructions

1. Make a slurry out of 1/2 tsp sugar, 1 tsp light soy sauce, and 1 tsp cornstarch. Stir in to the ground pork. After 30 seconds, add 1 tsp vegetable oil, and mix well.
2. Chop long beans into 2 inch long strips.
3. Boil a pot of water, add 1 tsp vegetable oil, and 1 tsp salt. Blench the long beans.
4. Hot pan, 1 tbsp vegetable oil, 1 smashed garlic clove, 1/2 tsp salt. Stir for 10 seconds. Add blenched long beans. Cook for about 1 to 2 minutes. Set aside.
5. Hot pan, 1 tbsp vegetable oil, 2 clove of smashed garlic. Add ground pork and cook until they are all white.
6. Add 25g black beans (1-1/2 tbsp ?), stir well. Add 1/3 cup of water, and stir well. Add back long beans. Stir well and ready to serve.

开水烧上去

活肉末，腌料汁的碗腾出来

切豇豆，放入腾出来的碗中

水开焯豇豆

过筛，甩干

锅擦干，开始炒菜

先炒豇豆

再炒猪肉末

然后豇豆回锅

出锅乘盘

# Find Corresponding English Expression

不顺手

讲究

一气呵成

Preheat the oven to X degrees.

Take out the flant steak, and baking tray. Tear a piece of perchment paper. Lay the steak on the paper. Take it into the oven and set a timer on the microwave or phone.

闷在里面



# Stir-fried Bok Choy

## Ingredient



## Instructions





