# magepov
Magento EAV Attribute Inspector. Command line utility to inspect a few attributes from a few entities (only products by now)

## How to install

Just copy the magepov script to a directory in PATH. 

A good choice is to copy it to ~/bin. Ensure ~/bin is in system PATH and the script has execution permissions.

```sh
mkdir -p ~/bin && wget -qO ~/bin/magepov https://raw.githubusercontent.com/manelio/magepov/master/magepov && chmod +x ~/bin/magepov
```

or

```sh
mkdir -p ~/bin && curl -so ~/bin/magepov https://raw.githubusercontent.com/manelio/magepov/master/magepov && chmod +x ~/bin/magepov
```

You can also copy the script to Magento shell directory, and invoke it as any other shell script: php shell/magepov (from Magento root).


```sh
$ magepov
Magento EAV Attribute Inspector.
Command line utility to inspect a few attributes from a few entities (only products by now)
Start typing some attributes and SKUs or product IDs. Use + at the end of SKU or ID to add child products.
Ex: 873+ msj006 price special_price status

% msj006 price

        |price                                
        admin   default   french    german    
----------------------------------------------
msj006  160.00  {160.00}  {160.00}  {160.00}  

% status

        |price                                |status                         
        admin   default   french    german    admin  default  french  german  
------------------------------------------------------------------------------
msj006  160.00  {160.00}  {160.00}  {160.00}  1      {1}      {1}     {1}     

% visibility

        |price                                |status                         |visibility                     
        admin   default   french    german    admin  default  french  german  admin  default  french  german  
--------------------------------------------------------------------------------------------------------------
msj006  160.00  {160.00}  {160.00}  {160.00}  1      {1}      {1}     {1}     1      {1}      {1}     {1}     

% 873+ special_price

          |price                                |status                         |visibility                     |special_price                  
          admin   default   french    german    admin  default  french  german  admin  default  french  german  admin  default  french  german  
------------------------------------------------------------------------------------------------------------------------------------------------
msj006    160.00  {160.00}  {160.00}  {160.00}  1      {1}      {1}     {1}     1      {1}      {1}     {1}            {}       {}      {}      
shw003    390.00  {390.00}  {390.00}  {390.00}  1      {1}      {1}     {1}     4      {4}      {4}     {4}            {}       {}      {}      
shw0036   390.00  {390.00}  {390.00}  {390.00}  1      {1}      {1}     {1}     1      {1}      {1}     {1}            {}       {}      {}      
shw0037   390.00  {390.00}  {390.00}  {390.00}  1      {1}      {1}     {1}     1      {1}      {1}     {1}            {}       {}      {}      
shw0038   390.00  {390.00}  {390.00}  {390.00}  1      {1}      {1}     {1}     1      {1}      {1}     {1}            {}       {}      {}      
shw0039   390.00  {390.00}  {390.00}  {390.00}  1      {1}      {1}     {1}     1      {1}      {1}     {1}            {}       {}      {}      
shw00310  390.00  {390.00}  {390.00}  {390.00}  1      {1}      {1}     {1}     1      {1}      {1}     {1}            {}       {}      {}      

% :c
% 835+ hdb001 price special_price status

          |price                                |special_price                  |status                         
          admin   default   french    german    admin  default  french  german  admin  default  french  german  
----------------------------------------------------------------------------------------------------------------
Pwt004    240.00  {240.00}  {240.00}  {240.00}         {}       {}      {}      1      {1}      {1}     {1}     
Pwt004xs  240.00  {240.00}  {240.00}  {240.00}         {}       {}      {}      1      {1}      {1}     {1}     
Pwt004s   240.00  {240.00}  {240.00}  {240.00}         {}       {}      {}      1      {1}      {1}     {1}     
Pwt004m   240.00  {240.00}  {240.00}  {240.00}         {}       {}      {}      1      {1}      {1}     {1}     
Pwt004l   240.00  {240.00}  {240.00}  {240.00}         {}       {}      {}      1      {1}      {1}     {1}     
Pwt004xl  240.00  {240.00}  {240.00}  {240.00}         {}       {}      {}      1      {1}      {1}     {1}     
hdb001    25.00   {25.00}   {25.00}   {25.00}          {}       {}      {}      1      {1}      {1}     {1}     

% 

```
