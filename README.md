# Supreme-Commander-FA-patch
This is not unofficial patch for SupCom FA which fixed some bugs in engine.


### Currently, it provides next fixes:
- [x] Fix no-rush timer to work with any value in minutes up to 109 mins. 
- [x] Fix wall selection - now double mouse click select all of them, just like any other units;
- [ ] Fix tech 4 factory selection


#### How to use 

If you just want to fix your game, download **supremecommander.fa-patch.exe**, put it into **bin** directory of your game and then run.

Use [x64dbg tool](https://x64dbg.com/#start) to debug exe file and use **database.dd32** to get actual information about changes in program.

**SupremeCommander FA.dUP2** is a project to [diablo2oo2](http://download.cnet.com/windows/diablo2oo2/3260-2094_4-10181657-1.html) and allows you to create your own patch file.

#### In order to have custom no-rush timer options you have to:
Open **gamedata\lua.scd** by any archiver such WinRar on 7zip and navigate to **lua\ui\lobby**  
When open **lobbyOptions.lua** with your favorite text editor and change following code:


````lua
{
    default = 1,
    label = "<LOC lobui_0316>No Rush Option",
    help = "<LOC lobui_0317>Enforce No Rush rules for a certain period of time",
    key = 'NoRushOption',
    pref = 'Lobby_NoRushOption',
    values = {
        {
            text = "<LOC lobui_0318>Off",
            help = "<LOC lobui_0319>Rules not enforced",
            key = 'Off',
        },
        {
            text = "<LOC lobui_0320>5",
            help = "<LOC lobui_0321>Rules enforced for 5 mins",
            key = '5',
        },
        {
            text = "<LOC lobui_0322>10",
            help = "<LOC lobui_0323>Rules enforced for 10 mins",
            key = '10',
        },
        {
            text = "<LOC lobui_0324>20",
            help = "<LOC lobui_0325>Rules enforced for 20 mins",
            key = '20',
        },
    },
}
````

You have to add your values into values array with the same semantic as other options. 

For example, to get 30 mins just add this code at after the last element
````lua
{
     text = "<LOC lobui_0324>30",
     help = "<LOC lobui_0325>Rules enforced for 30 mins",
     key = '30',
}
````
You also can change tooltips in lua.scd\lua\ui\help\tooltips.lua but it's not necessary. 
