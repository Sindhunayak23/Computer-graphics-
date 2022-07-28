#ifdef __APPLE__
#include <GLUT/glut.h>
#else
#include <GL/glut.h>
#endif
#include<math.h>

#include <stdlib.h>
float z_viewvol= -120;
float ypos=-1;
float xl=-1,xr=-1;
float xpos=-1,y=-1;
void DrawCircle(float cx, float cy, float r, int num_segments){


        glBegin(GL_TRIANGLE_FAN);
for (int i = 0; i < num_segments; i++)
{
float theta = 2.0f * 3.1415926f * float(i) / float(num_segments);//get the current angle
float x = r * cosf(theta);//calculate the x component
float y = r * sinf(theta);//calculate the y component
glVertex2f(x + cx, y + cy);//output vertex

}
glEnd();
}


void clouds(){
if(xl>=-300) {
    xl-=0.2;
}
if(xr<=400) {
    xr+=0.2;
}
    glColor3f(0.0,0.0,0.0);
    glBegin(GL_LINE_LOOP);
    glVertex2i(320,200);
    glVertex2i(360,200);
    glVertex2i(360,130);
    glVertex2i(320,130);
    glEnd();
    glBegin(GL_LINES);
    glVertex2i(320,150);
    glVertex2i(360,150);
    glEnd();
    glBegin(GL_LINES);
    glVertex2i(320,130);
    glVertex2i(315,55);
    glEnd();
    glBegin(GL_LINES);
    glVertex2i(360,130);
    glVertex2i(365,55);
    glEnd();
    glBegin(GL_LINES);
    glVertex2i(317,80);
    glVertex2i(364,80);
    glEnd();
    glBegin(GL_LINES);
    glVertex2i(317,80);
    glVertex2i(340,130);
    glEnd();
    glBegin(GL_LINES);
    glVertex2i(340,130);
    glVertex2i(364,80);
    glEnd();

    glColor3f(0.0, 0.0, 0.0);
    DrawCircle(120, 162, 10, 2000);
    DrawCircle(120, 172, 3, 2000);

    glBegin(GL_LINES);
    glVertex2i(120,162);
    glVertex2i(120,70);
    glEnd();
    glBegin(GL_LINES);
    glVertex2i(123,162);
    glVertex2i(125,70);
    glEnd();
    glBegin(GL_LINES);
    glVertex2i(117,162);
    glVertex2i(115,70);
    glEnd();
    glBegin(GL_LINES);
    glVertex2i(125,162);
    glVertex2i(127,70);
    glEnd();
    glBegin(GL_LINES);
    glVertex2i(115,162);
    glVertex2i(113,70);
    glEnd();
    glColor3f(1.0, 1.0, 1.0);

    glPushMatrix();
    glTranslatef(xl,0.0,0.0);
    DrawCircle(45, 220, 50, 2000);//1
    DrawCircle(65, 150, 50, 2000);//1
    DrawCircle(75,40, 80, 2000);//2
    glPopMatrix();

    glPushMatrix();
    glTranslatef(xr,0.0,0.0);
    DrawCircle(395, 70, 60, 2000);//1
    DrawCircle(405,90, 80, 2000);//2
    DrawCircle(415, 200, 55, 2000);//3
    glPopMatrix();

    DrawCircle(420,50, 80, 2000);//2
    DrawCircle(100, 30, 55, 2000);//3
    DrawCircle(300, 3, 55, 2000);//3
    DrawCircle(200, 3, 60, 2000);//1

}

void rocketcl(){
    glColor3f(1.2, 0.0, 0.0);
    DrawCircle(230, 420, 28, 2000);
    glColor3f(1.0, 1.0, 1.0);
    DrawCircle(231, 338, 19, 2000);
    DrawCircle(231, 338, 19, 2000);
    DrawCircle(231, 338, 19, 2000);
    DrawCircle(190, 371, 6, 2000);
    DrawCircle(271, 371, 6, 2000);

    DrawCircle(230, 129, 23, 2000);
    glBegin(GL_POLYGON);
    glVertex2i(222,120);
    glVertex2i(238,120);
    glVertex2i(238,100);
    glVertex2i(222,100);
    glEnd();
}
void rocket() {
    glPushMatrix();
if(ypos<=400) {
    ypos+=0.1;
}
else
{
    ypos=ypos-400;
}
//glTranslatef(0.0,ypos,0.0);
//glScalef(1.5,1.9,3);
glColor3f(1.2,0.0,0.0);
glBegin(GL_POLYGON);
glVertex2i(202,162);
glVertex2i(202,420);
glVertex2i(259,420);
glVertex2i(259,162);
glEnd();

glColor3f(1.0,1.0,1.0);              //Inside rectangle
glBegin(GL_POLYGON);
glVertex2i(212,162);
glVertex2i(212,335);
glVertex2i(250,335);
glVertex2i(250,162);
glEnd();

glColor3f(1.0,1.0,1.0);
glBegin(GL_POLYGON);
glVertex2i(265,162);
glVertex2i(265,370);
glVertex2i(277,370);
glVertex2i(277,162);
glEnd();

glColor3f(1.0,1.0,1.0);
glBegin(GL_POLYGON);
glVertex2i(184,162);
glVertex2i(184,370);
glVertex2i(196,370);
glVertex2i(196,162);
glEnd();

glColor3f(1.0,1.0,1.0);           //Horizontal rectangle
glBegin(GL_POLYGON);
glVertex2i(175,162);
glVertex2i(175,140);
glVertex2i(286,140);
glVertex2i(286,162);
glEnd();

glColor3f(1.0,1.0,1.0);
glBegin(GL_POLYGON);
glVertex2i(175,162);
glVertex2i(212,250);
glVertex2i(250,250);
glVertex2i(286,162);
glEnd();

glColor3f(1.0,0.0,0.0);        //red left
glBegin(GL_POLYGON);
glVertex2i(187,130);
glVertex2i(168,80);
glVertex2i(187,38);
glVertex2i(207,80);
glEnd();
glColor3f(1.0,0.9,0.0);         //yellow left
glBegin(GL_POLYGON);
glVertex2i(187,130);
glVertex2i(172,80);
glVertex2i(187,40);
glVertex2i(203,80);
glEnd();
glColor3f(1.0,1.0,1.0);          //Booster left
glBegin(GL_POLYGON);
glVertex2i(180,110);
glVertex2i(180,140);
glVertex2i(195,140);
glVertex2i(195,110);
glEnd();



glColor3f(1.0,0.0,0.0);         //red right
glBegin(GL_POLYGON);
glVertex2i(273,130);
glVertex2i(254,80);
glVertex2i(273,38);
glVertex2i(293,80);
glEnd();
glColor3f(1.0,0.9,0.0);           //yellow right
glBegin(GL_POLYGON);
glVertex2i(273,130);
glVertex2i(258,80);
glVertex2i(273,40);
glVertex2i(289,80);
glEnd();
glColor3f(1.0,1.0,1.0);          //Booster right
glBegin(GL_POLYGON);
glVertex2i(266,110);
glVertex2i(266,140);
glVertex2i(281,140);
glVertex2i(281,110);
glEnd();



glColor3f(0.3,0.3,0.6);          //Down Triangle
glBegin(GL_POLYGON);
glVertex2i(175,140);
glVertex2i(286,140);
glVertex2i(290,135);
glVertex2i(230,110);
glVertex2i(170,135);
glEnd();
rocketcl();
glPopMatrix();
}




void init()
{
    glClearColor(1,1,1,0);
    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    gluOrtho2D(0.0,500.0,0.0,500.0);
    glMatrixMode(GL_MODELVIEW);
}

void display(void)
{
glClearColor(0,0.5,1,0);
glClear(GL_COLOR_BUFFER_BIT);
glLoadIdentity();

if(y<=-1) {
    y-=0.3;
}
glPushMatrix();
glTranslatef(0.0,y,0.0);
glColor3f(0.0,0.0,0.0);          //Booster right
glBegin(GL_POLYGON);
glVertex2i(0,1000);
glVertex2i(500,1000);
glVertex2i(500,3000);
glVertex2i(0,3000);
glEnd();
glColor3f(1.0,1.0,1.0);

glPointSize(2);

glBegin(GL_POINTS);                 // points you can give here. i hv written few
glVertex2i(200,1500);
glEnd();
glBegin(GL_POINTS);
glVertex2i(100,1568);
glEnd();
glBegin(GL_POINTS);
glVertex2i(150,1600);
glEnd();
glBegin(GL_POINTS);
glVertex2i(400,1900);
glEnd();

glPopMatrix();

rocket();
if(xpos<=-1) {
    xpos-=0.4;
}
glPushMatrix();
glTranslatef(0.0,xpos,0.0);
clouds();
glPopMatrix();
glutPostRedisplay();
glutSwapBuffers();
}

int main(int argc, char **argv)
{
glutInit(&argc, argv);
glutInitWindowSize(1100, 650);
glutInitWindowPosition(0,0);
glutInitDisplayMode(GLUT_DOUBLE|GLUT_RGB);
glutCreateWindow("Rocket");
glutDisplayFunc(display);
init();
glutMainLoop();
}
