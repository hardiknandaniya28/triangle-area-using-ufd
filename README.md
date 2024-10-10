# triangle-area-using-ufd
this is programe for  understanding user  define function 
#include <stdio.h>
#include <math.h>

int verifyTriangle(float a, float b, float c);
float triangleArea(float a, float b, float c);

int main() {
  float a, b, c, area;
  printf("\n enter the sides of triangle:");
  scanf("%f%f%f", &a, &b, &c);
  if (verifyTriangle(a, b, c)) {
    area = triangleArea(a, b, c);
    printf("The area of the triangle is: %.2f\n", area);
  } else {
    printf("The given lengths do not form a triangle.\n");
  }
  return 0;
}

int verifyTriangle(float a, float b, float c) {
  if (a + b > c && a + c > b && b + c > a) {
    return 1; 
  } else {
    return 0;
  }
}

float triangleArea(float a, float b, float c) {
  float s = (a + b + c) / 2;
  float area = sqrt(s * (s - a) * (s - b) * (s - c));
  return area;
}
