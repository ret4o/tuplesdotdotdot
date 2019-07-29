# tuplesdotdotdot
For people and things, that went before! 
Half-sine fourier series messing about. -a



    import pylab

    import numpy as np
    A = 8/(np.pi**2) #A= constant
    x = np.arange(0,1,0.01) #Defining the range of x values from 0 to 1 with step 0.01


    
    yi=[]
    s=0 
    ytotal= [0.0]*100 #this will be used to find the total sum 
    for i in range(1,1000,2): #a step of 2 is used to replace the increments from 1-3-5 for the fourier series
    
        
        
        #alternating + or - for the beginning of our series
        
        yi.append( ((-1)**s)* np.sin(i*np.pi*x) / (i**2) * A) 
        #appends 100 values for each iteration of i - yi is a multidimensional array
   
    
    
        pylab.plot(x,yi[s],linewidth=2,color='k') 
    
    #with each iteration of i, a plot is drawn (i ->1,3,5,7...)
    
    
        ytotal+=(yi[s])
    
    #its important that the ytotal dimensions are definined earlier to avoid any issues with indices being out of range. ytotal has the same size as our yi. By iterative addition our ytotal plot becomes smoother. 
    s+=1
    
    
    pylab.plot(x,ytotal,linewidth=1) #
