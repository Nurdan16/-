package robin;

import java.util.Scanner;

public class Robin {

    public static void main(String args[])
	{
		Scanner in=new Scanner(System.in);

        System.out.println("Барлығы канша процесс орындалады - ");
        int num=in.nextInt();
        int B[]=new int[num];
        
        for(int i=0;i<num;i++)
		{
            System.out.println(" p"+(i+1)+"тің созылу уақыты-");
            B[i]=in.nextInt();
		}

        System.out.println("Кванттық уақытты енгізіңіз-");
        int q=in.nextInt();
        int wait[]=new int[num];
        
        
    
        int total;
		
		
        
       do
       {
       for(int i=0;i<num;i++){
	if(B[i]>q){
	 for(int j=0;j<num;j++){
	  if(j!=i && B[j]!=0){
	   wait[j]+=q;
	  }
	 }
	B[i]-=q;
	}
	else{
          for(int j=0;j<num;j++){
	    if(j!=i && B[j]!=0){
		wait[j]+=B[i];
	    }
	  }
	  B[i]=0;		
	}
       }
		   
	total=0;
	for(int i=0;i<num;i++){
		total+=B[i];
	}
		   
	}
       while(total!=0);  
		System.out.println("Process\t\t\twaiting time");
		float total_wait=0;
		for(int i=0;i<num;i++){
		 System.out.println("p"+(i+1)+"\t\t\t"+wait[i]);
	         total_wait+=wait[i];
		}
		System.out.println("Average waiting time is: "+(total_wait/num));
	}
}
