# Getting Started

## What the program does.
  The program is a reverse batching program that utilizes information from a series of stored, static and dynamic database of stored products and enables the operator to make a series of selections to run batches and print tickets for both company and client records.

## How to run it
  To run the program we use the RiceLake 1280 Industrial Programable Indicator and upload the *.rev and reverse.cod file to the indicator. 

# Notes
First thing at boot up -- no scales but shows the selection for the customer

`procedure Ready`

then is goes to the scales display with the recipe db underneath 
<br>
then you select a recipe and then it display a prompt for user entry</br> 
```
how much agregate is going to be in the mix?
```
-------------------------------------------------------------
NOTE: At this point once the user enters the amount of agregate for the mix,
based on the recipe that is chosen, it will determine the target values for cement and total tons that need to be reached.
-------------------------------------------------------------

<h2>Then the batch starts</h2>
<br>

# Info for us about the program
<ul>
  <li>Scale 1 = Cement</li>
  <li>Scale 2 = Sand Mix</li>
  <li><strong>Customer name</strong> is the only required entry</li>
</ul>

# About the batch procedure
<ul>
  <li>Printed value needs to be the weight at the time of print</li>
  <li>Target weight = Initial weight - Target Value</li>
  
  - To be used for creating the target value the program will actually use relative to the weight being read on the scale.

  <li>Printed value = initial weight - weight @ time of print</li>
  
  - This is what will be used as the active weight in displaying the bar graph level
</ul>

### Batch Process
```pascal
// initial weight = live weight at time of batch start
// live weight = live weight during batch cycle
// live weight in truck (material drawn from initial weight on scale) = initial weight - live weight
// level shown in bar graph = (live weight/target value from db) * 100
```

### Bar Graph Process
``` pascal

```