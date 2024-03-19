#include "colors.inc"  
#include "textures.inc"
#include "woods.inc"
#include "glass.inc"

#declare Pigment_1 = 
pigment{ crackle
         turbulence 0.35 scale 0.45
         color_map{
          [0.00 color rgb<1,1,1>*0]
          [0.08 color rgb<1,1,1>*0]
          [0.40 color rgb<1,0.55,0>]
          [1.00 color rgb<1,1,0.8>]
         } 
}


background{
rgb<0.2,0.2,0.4>
}   
camera {
 angle 80
 //location <5,5,5> 
 //location <10,8,10> //сыр
 location <30,5,20> //стол
 //location <48,20,48> //cтол
 //location <-70,42,-70>  //лестница
 //location <80,40,140> //
 //location <0,30,0> //над столом

 
 look_at 0
 //look_at <-65,30,-65>
}

light_source {
    <10,20,0>
    color White
}
light_source { 
    <60,50,60>
    color White
} 
//-------------------------------------------- 
#declare Amplitude = 40;
#declare Wing =
union{
prism{
    0,0.2,6
    <0,0>
    <1.5,2.5>
    <5,3.5>
    <5,0.5>
    <4,-1>
    <2.2,-1.2>
}
prism{
    0,0.2,3
    <0,0>
    <2,-1.5>
    <1,-4>
    
}
}
#declare ButterFly = 
union{
object{Wing
  rotate <0,0,Amplitude*sin( clock*0.5*pi)>
}
object{Wing
rotate<0,0,180>
 rotate <0,0,-Amplitude*sin( clock*0.5*pi)>
}
cylinder{
    <0.01,0.01,0.5>, <0.01,0.01,-1>, 0.2
}
	
	
	
pigment{ spiral1 10 //number of arms
         color_map{[0.0 color rgb <1,1,1>]
                   [0.5 color rgb <1,1,1>]
                   [0.5 color rgb <1,0,0>]
                   [1.0 color rgb <1,0,0>]
                  }//end of color_map
        }

}






















//-------------------------------------------- 
//оси 
//-------------------------------------------- 
#declare XYZ = 
union{
cylinder {
    0,10*x,0.03
    pigment {Red}
}
cylinder {
    0,3*y,0.03
    pigment {Green}
}
cylinder {
    0,10*z,0.03
    pigment {Blue}
}
}
//--------------------------------------------

//клетчатый пол 
#declare Floor =
prism{
    -0.5,0,4
    <70,70>,<-70,70>,<-70,-70>,<70,-70>  
    translate<0,-12,0>
    pigment{
    checker Black White scale 2
    }
}

           
//сыр  c 1 do 3 
#declare Cheese =
difference{
    prism{
        0,3,3
        <3,0>
        <0,3>
        <0,0>
        pigment{Pigment_1}
             
        rotate <0,5,0>
        translate<0,1,0>
    }
    cylinder{
        <3,3,3>, <1,1,1>, 0.3
        pigment{Yellow}
    }
    cylinder{
        <3,3,3>, <1,1,1>, 0.3
        translate <0,1,0>
        pigment{Yellow}
    }
    cylinder{
        <3,3,3>, <1,1,1>, 0.3
        translate <0,2,0>
        pigment{Yellow}
    }
    cylinder{
        <3,3,3>, <0.4,0.4,0.4>, 0.3
        translate <0,2,2>
        pigment{Yellow}
    }
    cylinder{
        <3,3,3>, <0.3,0.3,0.3>, 0.3
        translate <2,2,0>
        pigment{Yellow}
    }
    cylinder{
        <1,4,1>, <1,2.8,1>, 0.3
        translate <0,0.4,0.4>
        pigment{Yellow}
    }
    cylinder{
        <1,4,1>, <1,2.8,1>, 0.3
        translate <0.6,0.4,-0.5>
        pigment{Yellow}
    }
} 
//тарелка c 0 do 2
#declare Plate =
difference{
    cone{
        <0,0,0>, 2
        <0,1.5,0>, 5  
        pigment{ color rgb <0.35,0.45,1>}
        normal { spiral2 10
          bump_size 0.75 sine_wave
       } // end of normal
       
    } 
 
    cone{
        <0,1,0>, 4
        <0,3,0>, 8   
        pigment{Grey}
    }
}


//стол
#declare Table =
difference{
    box{
        <20,0,10> 
        <-20,-12,-10>
        texture { pigment { P_WoodGrain18A color_map { M_Wood18A }}}
    }
    
    box{
        <21,-1,9> 
        <-21,-16,-9> 
        texture { pigment { P_WoodGrain18A color_map { M_Wood18A }}}
    } 
    box{
        <19,-1,11> 
        <-19,-16,-11> 
        texture { pigment { P_WoodGrain18A color_map { M_Wood18A }}}
    }
    
    
    
}
//стул
#declare ColorYelGren = 
color_map{ [ 0.00 color rgb<0.50, 0.80, 0.00> ]
                [ 0.02 color rgb<1.00, 0.80, 0.00> ]
                [ 0.05 color rgb<0.00, 0.00, 0.00> ]
                [ 0.25 color rgb<0.00, 0.00, 0.00> ]
                [ 0.50 color rgb<1.00, 1.00, 1.00> ]
                [ 0.52 color rgb<0.00, 0.00, 0.00> ]
                [ 0.55 color rgb<1.00, 0.50, 0.00> ]
                [ 0.65 color rgb<1.00, 1.00, 0.00> ]
                [ 0.67 color rgb<1.00, 1.00, 0.00> ]
                [ 0.71 color rgb<0.00, 1.00, 0.00> ]
                [ 0.75 color rgb<0.00, 0.00, 0.00> ]
                [ 1.00 color rgb<0.00, 1.00, 1.00> ]
              } 
#declare ChairLeg =
cylinder {
    <0,-2,0>,<0,5,0>,0.35
}
#declare Chair = 
union{
 object{ChairLeg
    translate<0.5,0,0.5>}
 object{ChairLeg
    translate<6,0,6>}
 object{ChairLeg
    translate<6,0,0.5>}
 object{ChairLeg
    translate<0.5,0,6>}
 box{
    <6.5,5.2,6.5>
    <0,5,0>
    texture {
        pigment{
           tiling 18 
              color_map{ColorYelGren} 
           scale 0.15
         } 
        finish { phong 1}
      }
 }
 box{
    <0.2,5,0>
    <0,14,6.5>
    rotate<0,0,10>
    translate<1,0,0>
    texture {
        pigment{
           tiling 21 
              color_map{ColorYelGren} 
           scale 0.15
         } 
        finish { phong 1}
      } 
				
     
 }
 pigment{Brown}
 
     

}
//диван
    
//забор
//ддом
#declare MainHouse = 
difference{
    box{
        <71,60,71>
        <-71,-18,-71>
    }
    box{
        <70,54,70>
        <-70,33,-70> 
         pigment{Brown}
    }
    box{
        <70,28,70>
        <-70,-13,-70>
    }
    box{
        <-50,40,-40>
        <-70,20,-70>
    }
    box{
      <60,25,81>
      <30,-13,60>
    }
    box{
      <25,25,81>
      <-10,-13,60>
    }
    box{
      <60,53,81>
      <10,33,60>
    }
    box{
      <73,53,65>
      <69,33,-20>
    }
    
    texture {Rosewood}
    
    
}
#declare Windows = 
union{
    box{
      <60,25,71>
      <30,-13,70>
      material{M_Glass}
    }
    box{
      <25,25,71>
      <-10,-13,70>
       material{M_Glass}
    }
    box{
      <60,53,71>
      <10,33,70>
      material{M_Glass3}
     
    }
    box{
      <71,53,65>
      <70,33,-20>
       material{M_Glass3}
      
    }
}
//intersection{
//    object{MainHouse}
//    object{Windows}
//    //material{M_Glass}
//    pigment{Red}
//}

#declare OutHouse = 
difference{
    box{
       <120,60,90>
       <-31,-18,-31>
       
    }
    box{
       <110,28,100>
       <-32,-13,-32>
       
    }
    box{
       <130,54,100>
       <-28,33,-28>
       
    }
    box{
       <70,54,70>
       <-80,33,-80>
       
    }
    box{
       <130,28,80>
       <60,-13,-60>
       
    }
    texture{ pigment{ White_Marble }
           normal {
             pigment_pattern{
               Pigment_1
             } // pigment_pattern
             0.5 // BUMP_SIZE
           } // end of normal
           finish { phong 1 }
         }

}
#declare Kitchen = 
union{
    object { Chair 
        translate<-15,-10,5>
        rotate<0,90,0>}
    object { Chair 
        translate<-25,-10,-3>
        rotate<0,0,0>}
    object { Chair 
        translate<-15,-10,-10>
        rotate<0,90,0>}
    object { Chair 
        translate<-23,-10,15>
        rotate<0,140,0>}
    object { Table }
    object { Cheese } 
    object { Plate }

}
#declare Grass =
prism{
    -0.5,0,4
    <200,200>,<-200,200>,<-200,-200>,<200,-200>  
    translate<0,-18,0>
    pigment{Green}
}

union{
    //object {XYZ}
    //object { Floor }
    //object { Grass }
    //object {MainHouse}
    //object {Windows}
    //object {OutHouse} 
    object {Kitchen}
    //object {Table}
    object{ButterFly
    translate<0,7,0>}


}