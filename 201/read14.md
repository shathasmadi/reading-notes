## transforms

2d transforms :

2d rotate : transform: rotate 

2d scale ; tranform: scale (x,y)

2d translate : transform: translate(x,y)

2d skew : transform ; skew(x,y) ( cant be added to 3d transforms)

for 3d transforms we can use the above in addition to perspective 

## transitions and animitions 

The easiest way for determining styles for different states is by using the :hover, :focus, :active, and :target pseudo-classes.

background: #2db34a;
  border-radius: 6px
  transition-property: background, border-radius;(determines exactly what properties will be altered in conjunction with the other transitional properties)
  transition-duration: .2s, 1s;(duration in which a transition takes place)
  transition-timing-function: linear, ease-in;(the speed in which a transition will move.)
  transition-delay: 0s, 1s;(how long a transition should be stalled before executing. )
we can use the same but insted of transition  use animation 
## 8 simple css will wow your users 
1. fade in
.fade
{
        opacity:0.5;
}
.fade:hover
{
        opacity:1;
}

2. change color 


.color:hover
{
        background:#53a7ea;
}
3.grow and shrink 

.grow:hover
{
        -webkit-transform: scale(1.3);
        -ms-transform: scale(1.3);
        transform: scale(1.3);
}
to shrink we can use smaller numbers
4. rotate elemnts


.rotate:hover
{
        -webkit-transform: rotateZ(-30deg);
        -ms-transform: rotateZ(-30deg);
        transform: rotateZ(-30deg);
}

5. square to circle 

.circle:hover
{
        border-radius:50%;
}
6. 3d shadow 

.threed:hover
{
        box-shadow:
                1px 1px #53a7ea,
                2px 2px #53a7ea,
                3px 3px #53a7ea;
        -webkit-transform: translateX(-3px);
        transform: translateX(-3px);
}
7.swing 
8.insert box 


.border:hover
{
        box-shadow: inset 0 0 0 25px #53a7ea;
}