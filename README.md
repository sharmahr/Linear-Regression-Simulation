# Linear-Regression-Simulation
Linear Regression Simulation

Linear regression is a linear approach to modelling the relationship between a scalar response (or dependent variable) and one or more explanatory variables (or independent variables). There are two methods used in the simulation.
    
    1.Least Square Method
    2.Gradient descent
    
#Least Sqaure Method:
    
    void leastSqure() throws Exception{

      float xmean = 0, ymean = 0;
      for(PVector point: points){
        xmean += point.x/points.size();
        ymean += point.y/points.size();
      }

      float numerator = 0,denominator = 0;
      for(PVector point : points){
        numerator += (point.x-xmean)*(point.y-ymean);
        denominator += (point.x-xmean)*(point.x-xmean);
      }
      m = numerator/denominator;    // m slope of the line
      b = ymean - (m*xmean);        // y intercept of the line
    }
    
  
#Gradient Descent:

    void gradientDescent() throws Exception{
      float learning_rate = 0.01;
  
      for(PVector point : points){
        float x = point.x;
        float y = point.y;
        float guess = (m*x) + b;
        float error = y - guess;
        m = m + (error*x) * learning_rate;    // m is the slope of the line
        b = b + error * learning_rate;        // y intercept of the line
      }
    }


download processing at:
  https://processing.org/
