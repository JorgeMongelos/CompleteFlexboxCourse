# Designing Flex Items.

## Order - Reordering Flex Items.
```CSS
.container{
    display: flex;
    flex-flow: row wrap;
    justify-content: flex-start;
    align-content: space-between;
    align-items: flex-start;
    border: 1px solid #fff;
    height: 300px;
    width: 500px;
}

.container div{
    float: right;
}

.container div:nth-child(2){
    order: -1;
}

.container div:nth-child(5){
    order: 1;
}

.container div:nth-child(3){
    order: 5;
}
```
## Align-self - Stubborn Children

```CSS
.container{
    display: flex;
    flex-flow: row wrap;
/*  justify-content: flex-start; */ /* removing for align-self property to work properly */
    align-content: space-between;
    align-items: flex-start;
    border: 1px solid #fff;
    height: 300px;
    width: 500px;
}

.container div{
    float: right;
}

.container div:nth-child(2){
    order: -1;
    align-self: stretch;
}

.container div:nth-child(5){
    order: 1;
    align-self: flex-end;
}

.container div:nth-child(3){
    order: 5;
}
```
## Flex-grow - Letting Children Grow.

```CSS
.container{
    display: flex;
    flex-flow: row;
    border: 1px solid #fff;
    width: 800px;
}

.container div{
    float: right;
    width: 100px;
    margin: 0;
    flex-grow: 1;
}

.container div:nth-child(2){
    flex-grow: 3;
}

.container div:nth-child(3){
    
}
```
## Flex-shrink - Shrinking Flex Items.

```CSS
.container{
    display: flex;
    flex-flow: row;
    border: 1px solid #fff;
    width: 400px;
}

.container div{
    float: right;
    width: 200px;
    margin: 0;
}

.container div:nth-child(2){
    flex-shringk: 9;
}

.container div:nth-child(3){
    
}
```
## Flex Basis - Setting the base size.

```CSS
.container{
    display: flex;
    flex-flow: row;
    border: 1px solid #fff;
    width: 800px;
}
/* Flex-basis
 * container has a) space left or b) is overfull
 * look at a) flex grow and b) flex-shring
 * calculate portions each itmes will grow/shrink
 * add that to the base size
 */

.container div{
    float: right;
 /* flex-basis: 100px;
    flex-grow: 1; */ 
    flex: (grow value) (shrink value) (basis value); /* shorthand flor flex-grow, flex-shrink, flex-basis*/
    margin: 0;
}

.container div:nth-child(2){
    flex-shringk: 9;
}

.container div:nth-child(3){

}   
```
## Flexbox grids: creating responsive galleries #1(Minimal code)

```CSS
.grid{
    display: flex;
}

.gutters{
    margin: 10px 0 10px 10px;
}

.gutters > .cell{
    padding: 10px 0 0 10px;
}

.cell{
    flex: 1; /* 1 1 0% */
}

.cell > div{
    background-color: rgba(255, 255, 255, 0.7%);
    height: 100%;
    width: 10px;
}

.large{
    flex-grow: 3;
}
```
## Flexbox grids: creating responsive galleries #2(extra flexibility)

```CSS
.grid{
    display: flex;
}

.gutters{
    margin: 10px 0 10px 10px;
}

.gutters > div{
    padding: 10px 0 0 10px;
}

.gird div div{
    background-color: rgba(255, 255, 255, 0.7%);
    padding: 10px;
    width: 100%;
}

.half{
    flex-basis: 50%;
}

.third{
    flex-basis: 33.33333%;
}

.fourth{
    flex-basis: 25%;
}

.fifth{
    flex-basis: 20%;
}

.sixth{
    flex-basis: 16.66666%;
}
```
## Real Vertical Centering with Flexbox(no more vertical-align)

```CSS
.vcenter{
    display: flex;
    align-items: center;
    justify-content: center;
    height: 150px;
    border: 1px solid white;
}

nav{
    width: 400px;
}

li{
    list-style-type: none;
    flex-basis: 25%;
}

p{
    margin: 0;
}
```
## The Media Object Pattern

```CSS
.media{
    display: flex;
    flex-flow: row wrap;
}

.figure{
    flex: 1 1 30%;
    align-self: flex-start;
    order: 0;
}

.media-body{
    flex: 1 1 60%;
}

p{
    margin: 0 10px 20px 10px;
}
```
## The Holy Grail of CSS.

```CSS
body{
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    margin: 0;
}

#main{
    display: flex;
    flex-grow: 1;
}

#content{
    flex: 4 1 0%;
}

#secondary{
    flex: 1 1 0%;
}

#tertiary{
    flex: 1 1 0%;
}

#header, #footer{
    text-align:center;
    padding: 20px;
}
```
```HTML
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
    </head>
    <body>
        <header id="header">Header</header>
        <main id="main">
            <section id="content"|>
                Lorem ipsum dolor, sit amet consectetur adipisicing elit. Laboriosam distinctio dolor possimus quo voluptatum saepe. Enim delectus eos officiis necessitatibus! Ad consequatur, consectetur culpa totam hic id? Maxime, et deleniti.
            </section>
            <aside id="secondary">
                Lorem ipsum dolor, sit amet consectetur adipisicing elit. Laboriosam distinctio dolor possimus quo voluptatum saepe. Enim delectus eos officiis necessitatibus! Ad consequatur, consectetur culpa totam hic id? Maxime, et deleniti.
            </aside>
            <aside id="tertiary">
                Lorem ipsum dolor, sit amet consectetur adipisicing elit. Laboriosam distinctio dolor possimus quo voluptatum saepe. Enim delectus eos officiis necessitatibus! Ad consequatur, consectetur culpa totam hic id? Maxime, et deleniti.
            </aside>
            <footer>Footer.</footer>
        </main>
    </body>
</html>
```
