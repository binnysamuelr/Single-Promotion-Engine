# Single-Promotion-Engine
// (Promotion Statement 1)
/* I have implemented a simple promotion engine for a checkout process, 
using a Menu driven console application. 
This application can be used to calculate the total order 
value after applying the promotion code.*/













      using System; 

      public class PromotionEngine
      {

        public static void Main()
        {
          int TotalSKU, Opt, PromoOpt;

          // List of SKU id's
          List <char> SKUid = new List <char>();

          // List of UnitPrice for the SKU Id's
          List <int> UnitPrice = new List <int>();

          // List of Items from the SKU Id's 
          List <int> Items = new List <int>();

          // List of Promo Codes available 
          List <string> Promos = new List <string>();
  
          console.write("\n Promotion Engine \n");
          console.write("\n ----------------------\n");
          
          console.write("\n Input the total number of SKU id's:\n");
          TotalSKU = convert.ToInt32(console.ReadLine());

          console.write("\n Input {0} SKU id's followed by their Unit Prices: \n",TotalSKU);

          for (i=0;i < TotalSKU; i++)
          {
             // input SKU ID's
             console.write("\n SKU - {0}: \n",i);
             SKUid.Insert(i,console.ReadLine());
             // input Unit Price 
             console.write("\n Unit Price for {0}: \n",SKUid[i]);
             UnitPrice.Insert(i, convert. ToInt32 (console.ReadLine  ());
             // set number of items to 0
             Items.Insert(i, 0);
          }


          
          // Menu to access various operations.        
          console.write("\n Main Menu: \n");

          console.write("\n 1- Add Items.\n 2- Remove Items.\n 3- Apply Promo Code.\n 4- View Total Order Value. \n 5-Exit.\n");

          Opt = convert. ToInt32 (console.ReadLine  ());

          switch (Opt)
          {

          case 1:
          // Add items from respective SKU id''s. 
          console.write("\n Add required number of items, from available SKU ID's : \n");

          if (TotalSKU  <= 0)
          {
               console.write("\n No SKU's found.\n");
          }
          Else
          {
               for (i=0; i < TotalSKU; i++)
               {

                  console.write ("\n Enter number of items from SKU-{0}: for example :4\n", skuId [i];
                  items.insert (i, items[i] + convert. ToInt32 (console.ReadLine ());

                  console.write ("\n {0} items exist from SKU-{1} in cart", items [i], skuId[i]);
               }
           }
           console.write ("\n Building Cart Complete.");
           break;


           case 2:
           // Remove items from respective SKU id's
           console.write("\n remove items: \n"):
           if(TotalSkU<=0)
           {
             console.write("\n No SKU's found\n");
           }
           else
           {
             for(i=0; i < totalSKU; i++)
             {
               If(items[i] > 0)
               {
                 console.write("\n enter no.of items to be removed from SKU-{0}; for example: 4\n " SKUID[i]);
                 Items.insert(i,items[1]-convert.toint32(console.readline());
                 console.write("In {0} items exist from SKU-{1} in cart",items [i],SKUId[i]);
                }
             }
           }
           console.write("\n building cart complete");
           break;

           case 3:

           console.write("\n Apply promo code:\n");
           console.write("\n Available promo:\n");
           Promo myPromo=new Promo();

           // Fetch promo codes from Promo class.
           Promos = myPromo.GetPromoList();

           for(int i=1;i<=Promos.count;i++)
           {
             console.writeline("{0}-{1}",i,Promos[i-1]);
           }
           console.write ("choose your promo code\n");
           PromoOpt = convert.ToInt32 (console.ReadLine ());

           string res = myPromos.ApplyPromo(Promos[PromoOpt-1], skuId, UnitPrice, items);
           console. Writeline  (res);

           if  (res == "successful")
           {
             // update the promo code property in the promo code class
             myPromos.Promocode=Promos[PromoOpt-1];
           }
           break;

           case 4:

           console.writeline("\n order summary\n");
           OrderValve objOrdervalve=new OrderValue();
           int Totalvalue = objOrdervalue.OrderTotal;
         
           Promo objPromo=new Promo();
           string strPromo=objPromo.Promocode;
           if( strPromo == "")
           {
             // When Promo is not applied it gets the total value of items without the promo's
             int tot1= objOrdervalue.Gettot();
             console.write("\n total is {0}", tot1);
           }
           else
           {
             int tot2= objOrdervalue.OrderTotal;
             console.write("In total is {0}:",tot2);
           }
           break;
           
           Case 5:
             
           break;

           default:

           console.write(" input correct option\n");
           break;
          }
        }
      }
      
      
      // Implementing Promo class to attain independency, so that promo codes can be edited at later stages.

      Public class Promo
      {

        public List<string> ActivePromolist=new List<string>();
  
        Public List<string> GetPromoList()
        {
          // Promo: buy 'n' items of a SkU for a fixed price
          ActivePromolist.Insert(0,"NitemsFixedPrice");
          // Promo: buy SKU 1 & SKU 2 for a fixed price
          ActivePromolist.Insert(1,"SKU1SKU2FixedPrice");
     
          return Active promolist;
        }

        private string promocode;

        public string Promocode
        {
         get {return promocode;}
         set{promocode=value;}
         }

         public string ApplyPromo(string Promo, List<char> SKUid, List<int> UnitPrice, List<int> items)
         {
          int TotA, TotB, TotC, TotD, TotCD;
          int Total;
          string res="";
          if (Promo == "NitemsFixedPrice")
          {
            // Apply promo for first SKU i.e 'A'
     
            If(SKUid.ElementAtOrDefault(0)!=null)
            {
              string SKUidA=SKUid[0].toString();
              int UnitPriceA=UnitPrice[0];
              int itemA=items[0];

              if (itemsA == 0)
              {
                Tot [0] = 0;
              }
              else if(itemsA % 3 == 1)
              {
                int quo1 = itemsA / 3 ;
                TotA = (quo1 × 130) + (1 × UnitPriceA);
              }
              else if(itemsA % 3 == 2)
              {
                int quo2 = itemsA / 3 ;
                TotA = (quo2 × 130) + (2 × UnitPriceA);
              }
              else if(itemsA % 3 == 0)
              {
                int Quo3 = itemsA / 3;
                TotA = (Quo3 * 130);
              }
           }
           
           //apply promo for second SKU i.e 'B'
           If(SKUid.ElementAtOrDefault(1)!=null)
           {
             string SKUidB=SkUid[1].tostring();
             int UnitpriceB=Unitprice[1];
             int ItemB=items[1];

             if (itemsB == 0)
             {
               TotB=0;
             }
             else if (itemsB % 2 == 1)
             {
               int Quo4=itemsB / 2;
               TotB= (Quo4 × 45)+(1 × UnitpriceB);
             }
             else if (itemsB % 2 == 0)
             {
               int Quo5 = itemsB / 2;
               TotalB = (Quo5 × 45);
             }
           }
     //Total for 'C'
     If(SKUid.ElementAtOrDefault (2)!=null)
     {
     string SKUidC = SKUid[2].toString();
     int UnitpriceC = Unitprice[2];
     int ItemC = items[2];
     TotC = UnitPriceC × ItemC;
     }
     // Total for 'D'
     If(SKUid.ElementAtOrDefault (3)!=null)
     {
      string SKUidD=SKUid[3].toString();
      int UnitpriceD=Unitprice[3];
      int ItemD=items[3];
      TotD=unitpriceD × ItemD,
     }
     Total=TotA+TotB+TotC+TotD;
     Ordervalue obj=new Ordervalue ();
     obj.Ordertotal=Total;
     res="successful";

     Promocode="NitemsFixedPrice";
     }
     Else if(promo==SKU1SKU2FixedPrice")
     {
      If(SKUid.ElementAtOrDefault(0)!=null)
      {
        string SKUidA=SKUid[0].tostring();
        int unitpriceA=unitprice[0];
        int itemA = items [0];
        TotA=unitpriceA × itemA;
      }
      If(SKUid.ElementAtOrDefault (1)!=null)
      {
       stringSKUidB=SKUid[1].tostring();
       int unitpriceB=Unitprice[1];
       int itemB=items[1];
       TotB=unitpriceB × itemB;
      }
      if((SKUid.ElementAtOrDefault(2)==null))
      {
       TotC=0;
       TotD=0;
      }
      If(SKUid.ElementAtOrDefault(3)==null)
      {
       string SKUidC=SKUid[2].tostring();
       int UnitpriceC=Unitprice[2];
       int itemC=items[2];
       TotC=UnitpriceC×itemC:
      }
      Else
      {
       string SKUidC=SKUid[2].toString();
       int unitpriceC=unitprice[2];
       int itemC=items[2];
       string SKUidD=SKUid[3];
       int UnitpriceD= Unitprice[3];
       int itemD= items[3];
       If (ItemC > ItemD)
       {
        int not_match= itemC - itemD;
        TotCD=(ItemD×30)+(not_match×UnitpriceC);
       }
       Else if( itemD > itemC)
       {
       int Not_match1=itemD-itemC;
       TotCD=(itemC×30)+(Not_match1×UnitpriceD);
       }

       Total = TotA + TotB + TotC + TotCD;
       Ordervalue obj1 = new OrderValue ();
       Obj1.OrderTotal = Total ;
       res = "Successful ";
       Promocode = "SKU1SKU2FixedPrice";
       }
       return res;
     }

