# Derivative-code


#include <stdio.h>
#include <math.h>
#define N 100
void
main ()
{
  int i;
  float y[N], x[N],z[N];
  float a, b, dx = (b-a)/N;
  
  printf("Enter a range (a,b) to calcuate derivative\na = ");
  scanf("%f",&a);
  printf("b = ");
  scanf("%f",&b);
 
 dx = (b-a)/N;
 
  for (i = 0; i<=N; i++,a+=dx)
    {
      x[i] = a;
      y[i] = exp (-x[i]);
      z[i] = -exp(-x[i]);
    }
    
  printf ("\tx\t\te^(-x)\t\t(e^-x)'\t\t(e^-x)''\n");
  for (i = 0; i <= N-1 ; i++)
    {
      printf ("%10.2f\t%10.2f\t%10.2f\t%10.2f\n", x[i], y[i],
	      (y[i + 1] - y[i]) / (x[i + 1] - x[i]),(z[i + 1]-z[i])/(x[i+ 1]-x[i]));
    }
//printf("%10.2f\t%10.2f\t\n",x[b],y[b]);

}
