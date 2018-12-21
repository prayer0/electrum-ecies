#   E l e c t r u m   E C I E S  
  
 E l e c t r u m   E C I E S   j s   i m p l e m e n t ,   e n c r y p t / d e c r y p t   m e s s a g e   i n   B I E 1   f o r m a t ,   l i k e   E l e c t r u m / E l e c t r o n   T o o l s   - >   E n c r y p t / d e c r y p t   m e s s a g e .  
  
 # # #   U s a g e  
  
 E n c r y p t   a   m e s s a g e ,   s o   i t   c a n   b e   d e c r y p t e d   i n   E l e c t r u m / E l e c t r o n   C a s h   W a l l e t .  
  
 O r   d e c r y p t   m e s s a g e   E l e c t r u m / E l e c t r o n   C a s h   W a l l e t   e n c r y p t e d .  
  
 # # # #   I n s t a l l   v i a   N P M  
  
 ~ ~ ~ s h e l l  
 n p m   i n s t a l l   e l e c t r u m - e c i e s  
 ~ ~ ~  
  
 # # #   E x a m p l e s  
  
 # # # #   E n c r y p t   M e s s a g e   w i t h   R e c e i v e r ' s   P u b l i c K e y  
  
 ~ ~ ~ j a v a s c r i p t  
 c o n s t   E C I E S   =   r e q u i r e ( ' e l e c t r u m - e c i e s ' ) ;  
 / / R e c e i v e r ' s   P u b l i c K e y :   0 2 c 0 1 c 3 5 e e f 3 1 a c b 6 0 3 8 6 f 7 f b 8 e 0 2 6 7 f 0 8 f a f 5 7 2 4 d 1 b 2 f a 1 f 3 5 8 8 a 5 f e f 3 e 7 2 6 3 0 9  
 E C I E S . e n c r y p t ( ' H e l l o ' , ' 0 2 c 0 1 c 3 5 e e f 3 1 a c b 6 0 3 8 6 f 7 f b 8 e 0 2 6 7 f 0 8 f a f 5 7 2 4 d 1 b 2 f a 1 f 3 5 8 8 a 5 f e f 3 e 7 2 6 3 0 9 ' ) ;    
 / / ' Q k l F M Q M F m P d v j F e 8 W f o + J W m T p o + 3 3 L X c + 4 G 8 T h f a u c U 7 2 k i e b 6 l W E v 4 l a y T b 0 x 5 t z p i 6 l A 2 i t 8 r O / E L r X o m J q C 5 3 u B O d + D Z S z D h C S p K 6 S w R + I t t + P w = = '  
 / / B I E 1   u s e   e p h e m e r a l   k e y s ,   s o   c i p h e r t e x t   i s   d i f f e r e n t   e v e r y   t i m e .  
 ~ ~ ~  
  
 # # # #   D e c r y p t   B I E 1   M e s s a g e   w i t h   R e c e i v e r ' s   P r i v a t e K e y  
  
 ~ ~ ~ j a v a s c r i p t  
 c o n s t   E C I E S   =   r e q u i r e ( ' e l e c t r u m - e c i e s ' ) ;  
 / / R e c e i v e r ' s   P r i v a t e K e y : a 1 b 5 0 c 4 d 4 2 0 b 2 0 0 5 9 b 0 1 e 7 e e a 3 b 3 d 8 a 5 e 9 4 3 7 2 8 d f e d f 9 6 2 6 2 8 c a 1 8 d 0 4 b f a 2 c f c  
 / / D e c r y p t   A b o v e   M e s s a g e  
 E C I E S . d e c r y p t ( ' Q k l F M Q M F m P d v j F e 8 W f o + J W m T p o + 3 3 L X c + 4 G 8 T h f a u c U 7 2 k i e b 6 l W E v 4 l a y T b 0 x 5 t z p i 6 l A 2 i t 8 r O / E L r X o m J q C 5 3 u B O d + D Z S z D h C S p K 6 S w R + I t t + P w = = ' , ' a 1 b 5 0 c 4 d 4 2 0 b 2 0 0 5 9 b 0 1 e 7 e e a 3 b 3 d 8 a 5 e 9 4 3 7 2 8 d f e d f 9 6 2 6 2 8 c a 1 8 d 0 4 b f a 2 c f c ' )  
 / / < B u f f e r   6 8   6 5   6 c   6 c   6 f >  
 ~ ~ ~  
  
 # # # #   I   J u s t   W a n t   t h e   E C D H   K e y  
  
 ~ ~ ~ j a v a s c r i p t  
 c o n s t   E C I E S   =   r e q u i r e ( ' e l e c t r u m - e c i e s ' ) ;  
 c o n s t   P u b l i c K e y   =   r e q u i r e ( ' b s v ' ) . P u b l i c K e y ;  
 c o n s t   P r i v a t e K e y   =   r e q u i r e ( ' b s v ' ) . P r i v a t e K e y ;  
  
 v a r   e c d h _ k e y   =   E C I E S . e c d h _ k e y ( n e w   P u b l i c K e y ( [ R e c e i v e r   P u b k e y ] ) , n e w   P r i v a t e K e y ( [ S e n d e r / E p h e m e r a l   P r i v K e y ] ) )  
  
 v a r   i v = e c d h _ k e y . s u b a r r a y ( 0 , 1 6 ) ;  
 v a r   k e y _ a e s = e c d h _ k e y . s u b a r r a y ( 1 6 , 3 2 ) ;  
 v a r   k e y _ h m a c = e c d h _ k e y . s u b a r r a y ( 3 2 , 6 4 ) ;  
 ~ ~ ~  
  
 # # #   D o n a t i o n  
  
 I f   y o u   l i k e   i t .  
  
 B S V   a d d r e s s :   1 B H c P b c j R Z 9 Z J v A t r 9 n d 4 E Q 4 H b s U C 7 7 W D f  
  
 I ' m   a   s u p p o r t e r   o f   B S V ,   b u t   y o u   a r e   f r e e   t o   u s e   i t   o n   B T C / B C H   e t c .  
  
 # # #   L i c e n s e  
  
 B S D - 2 - C l a u s e 