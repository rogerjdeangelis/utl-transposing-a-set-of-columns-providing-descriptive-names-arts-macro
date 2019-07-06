# utl-transposing-a-set-of-columns-providing-descriptive-names-arts-macro
Transposing a set of columns providing descriptive names arts macro

    Transposing a set of columns providing descriptive names arts macro                                                         
                                                                                                                                
    This is becoming a broken record                                                                                            
                                                                                                                                
    Transpose macro by                                                                                                          
    AUTHORS: Arthur Tabachneck, Xia Ke Shan, Robert Virgile and Joe Whitehurst                                                  
                                                                                                                                
    github                                                                                                                      
    https://tinyurl.com/yybrcdz7                                                                                                
    https://github.com/rogerjdeangelis/utl-transposing-a-set-of-columns-providing-descriptive-names-arts-macro                  
                                                                                                                                
                                                                                                                                
    StackOverflow R                                                                                                             
    https://tinyurl.com/y67vsv3f                                                                                                
    https://stackoverflow.com/questions/56877279/error-the-id-value-xxxxxxxxxxxx-occurs-twice-in-the-same-by-group-when-trans   
                                                                                                                                
    macros                                                                                                                      
    https://tinyurl.com/y9nfugth                                                                                                
    https://github.com/rogerjdeangelis/utl-macros-used-in-many-of-rogerjdeangelis-repositories                                  
                                                                                                                                
    *_                   _                                                                                                      
    (_)_ __  _ __  _   _| |_                                                                                                    
    | | '_ \| '_ \| | | | __|                                                                                                   
    | | | | | |_) | |_| | |_                                                                                                    
    |_|_| |_| .__/ \__,_|\__|                                                                                                   
            |_|                                                                                                                 
    ;                                                                                                                           
                                                                                                                                
    data have;                                                                                                                  
    retain id weight;                                                                                                           
    input ID  Name$ Weight lipids plasma LOD;                                                                                   
    cards4;                                                                                                                     
    1 Lead 1.55 44.0 10.0 5.00                                                                                                  
    1 Mercury 1.55 222.0 100.0 75.00                                                                                            
    2 Lead 1.25 25.5 12.0 5.00                                                                                                  
    ;;;;                                                                                                                        
    run;quit;                                                                                                                   
                                                                                                                                
    WORK.HAVE total obs=3                                                                                                       
                                                                                                                                
     ID     WEIGHT    NAME       LIPIDS    PLASMA    LOD                                                                        
                                                                                                                                
      1      1.55     Lead         44.0       10       5                                                                        
      1      1.55     Mercury     222.0      100      75                                                                        
      2      1.25     Lead         25.5       12       5                                                                        
                                                                                                                                
                                                                                                                                
    *           _                                                                                                               
     _ __ _   _| | ___  ___                                                                                                     
    | '__| | | | |/ _ \/ __|                                                                                                    
    | |  | |_| | |  __/\__ \                                                                                                    
    |_|   \__,_|_|\___||___/                                                                                                    
                                                                                                                                
    ;                                                                                                                           
                                                                                                                                
    Fill in this template by transposing                                                                                        
                                                                                                                                
    Unique                                                                                                                      
    By Variables                                                                                                                
    =============                                                                                                               
    ID     WEIGHT  LIPIDS_LEAD  PLASMA_LEAD  LOD_LEAD LIPIDS_MERCURY   PLASMA_MERCURY   LOD_MERCURY                             
                                                                                                                                
     1      1.55                                                                                                                
     2      1.25                                                                                                                
                                                                                                                                
    *            _               _                                                                                              
      ___  _   _| |_ _ __  _   _| |_                                                                                            
     / _ \| | | | __| '_ \| | | | __|                                                                                           
    | (_) | |_| | |_| |_) | |_| | |_                                                                                            
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                           
                    |_|                                                                                                         
    ;                                                                                                                           
                                                                                                                                
    WORK.WANT total obs=2                                                                                                       
                                                                                                                                
                           LIPIDS_    PLASMA_                LIPIDS_    PLASMA_      LOD_                                       
    Obs    ID    WEIGHT      LEAD       LEAD     LOD_LEAD    MERCURY    MERCURY    MERCURY                                      
                                                                                                                                
     1      1     1.55       44.0        10          5         222        100         75                                        
     2      2     1.25       25.5        12          5           .          .          .                                        
                                                                                                                                
                                                                                                                                
    *          _       _   _                                                                                                    
     ___  ___ | |_   _| |_(_) ___  _ __                                                                                         
    / __|/ _ \| | | | | __| |/ _ \| '_ \                                                                                        
    \__ \ (_) | | |_| | |_| | (_) | | | |                                                                                       
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|                                                                                       
                                                                                                                                
    ;                                                                                                                           
                                                                                                                                
                                                                                                                                
    %utl_transpose(data=have, out=want, by=id weight, id=name, delimiter=_, var=lipids plasma lod,sort=id weight );             
                                                                                                                                
                                                                                                                                
