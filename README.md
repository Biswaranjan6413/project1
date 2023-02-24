public class EbTariff2 
{   
    double cost=0;
    double units=0;

    void logic(String category, double units)
    {
     if(category=="Domestic" || category=="domestic" || category=="Handloom" || category=="handloom" || category=="Handlooms" || category=="handlooms" ||
                category=="Old age homes" || category=="old age homes" || category=="Consulting rooms" || category=="consulting rooms") 
              {         
                if(category=="Handloom" || category=="handloom" || category=="Handlooms" || category=="handlooms") 
                  {
                    units= units - 200.00;
                         if(units<=0)
                            {
                             System.out.println("No charge for you!!!");
                            }
                    else if(units<=200)
                            {
                            cost= units*2.25;
                            System.out.println("Your payment "+ cost);
                            }
                    else if(units<=500.00) 
                            {
                             below500(units);
                            }
                    else if(units>=501.00 && units<=1000) 
                            {
                             above500(units);
                            }
                    else if(units>1000.00) 
                            {
                             above1000(units);   
                            }
                  }
                else if(units<=500.00) // Except handlooms category
                          { 
                           units= units - 100.00;
                   
                         if(units<=0)
                            {
                             System.out.println("No charge for you!!!");
                            }
                   else if(units<=100)
                           {
                            cost= units*2.25;
                            System.out.println("Your payment "+ cost);
                           }
                   else if(units<=500.00) 
                           {
                            below500(units);
                           } 
                          }
                   else if(units>=501.00 && units<=1000) 
                           {
                            above500(units);
                           }
                   else if(units>1000.00) 
                           {
                            above1000(units);
                           }     
                              
 }        }
    
    double until() //for above 500
    {
     double charge= 4.50;// 101-400
     double cost= 300*charge;
     
     charge= 6.00;// 401-500
     cost= (100*charge)+cost;
     return cost;
    }

    void noCharge()
    {
     System.out.println("No charges for you!!");
    }

    double below500(double units)// <=500
    {       
    if(units<=200)
      {
      double charge= 2.25;
      double cost= 100*charge;
      System.out.println("Your payment "+ cost);
      return cost;
      }
    else if(units>=201 && units<=400)
      {
      double charge= 2.25;
      double cost= 100*charge;

      charge= 4.50;
      cost= ((units-100)*charge)+cost;
      System.out.println("Your payment "+ cost);
      return cost;
      }
    else if(units>=401 && units<=500)
      {
      double charge= 2.25;
      double cost= 100*charge;

      charge= 4.50;
      cost= (200*charge)+cost;

      charge= 6.00;
      cost= ((units-300)*charge)+cost;
      System.out.println("Your payment "+ cost);
      return cost;
      }        
     return cost;
     }
    
    double above500(double units)// >500 <=1000
    {
     if(units>=501 && units<=600) //501-600
        {  cost= until();

         double charge= 8.00;
         cost= ((units-400)*charge)+cost;
         System.out.println("Your payment "+ cost);
        return cost;
        }
     else if(units>=601 && units<=800)
            { double charge=0;
              double cost=0;
             cost= until();

             charge= 8.00;
             cost= (100*charge)+cost;

             charge= 9.00;
             cost= ((units-500)*charge)+cost;
             System.out.println("Your payment "+ cost);
            return cost;
            }
     else if(units>=800 && units<=1000)
            { double charge=0;
              double cost=0; 
             cost= until();
                
             charge= 8.00;
             cost= (100*charge)+cost;

             charge= 9.00;
             cost= (200*charge)+cost;

             charge= 10.00;
             cost= ((units-700)*charge)+cost;
             System.out.println("Your bill is "+ cost);
           return cost;
           }
    return cost;
    }

    double above1000(double units)// >1000
    {  double charge=0;
       double cost=0;

     cost= until();

     charge= 8.00;
     cost= (100*charge)+cost;

     charge= 9.00;
     cost= (200*charge)+cost;

     charge= 10.00;// 801-1000
     cost= (200*charge)+cost;

     charge= 11.00;// >1000
     cost= ((units-900)*charge)+cost;
     System.out.println("Your bill  is "+ cost);
    return cost;
    }

public static void main(String args[])
{
    EbTariff2 obj = new EbTariff2();
    obj.logic("domestic", 16);
}
}
