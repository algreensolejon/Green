#include <GL/glut.h>

void display();
void reshape(int, int);



int main(int argc, char** argv)
{
    glutInit(&argc, argv);
    glutInitDisplayMode(GLUT_RGB);

    glutInitWindowPosition(300, 0); 
    glutInitWindowSize(600, 600); 
    glutCreateWindow("Mi3FinalTask"); 

    glutDisplayFunc(display);
    glutReshapeFunc(reshape);

    glClearColor(0.0f, 0.0f, 0.11f, 0.0f); 
    glutMainLoop(); 
}


void display()
{
    glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
    glLoadIdentity();
 
    // blue
  glColor4f(1.0f, 0.0f, 0.0f, 0.0f);
    glBegin(GL_QUADS); 
    glVertex2f(9.8, 0);
    glVertex2f(-9.8, 0);
    glVertex2f(-9.8, -5);
    glVertex2f(9.8, -5);
    
    // red
    glColor3f(0.0f, 0.0f, 1.0f);
    glBegin(GL_QUADS); 
    glVertex2f(9.8, 5);
    glVertex2f(-9.8, 5);
    glVertex2f(-9.8, 0);
    glVertex2f(9.8, 0);

 
  

    glEnd(); 
    glFlush(); 

    
    glColor3f(1.0, 1.0, 1.0); 
    glBegin(GL_TRIANGLES); 
    glVertex2f(-2, 0);
    glVertex2f(-9.8, 5);
    glVertex2f(-9.8, -5);

    glEnd(); 
    glFlush(); 

    
   

   // 3 star
    glColor3f(1,1,0); 
    glBegin(GL_QUADS);
    glVertex2f(-3.4, 0.4);
    glVertex2f(-4.2, 0.4);
    glVertex2f(-4.2, -0.4);
    glVertex2f(-3.4, -0.4);

   
  glColor3f(1,1,0);
    glBegin(GL_QUADS); 
    glVertex2f(-8.7, 3.8);
    glVertex2f(-9.5, 3.8);
    glVertex2f(-9.5, 3.0);
    glVertex2f(-8.7, 3.0);


    
    glColor3f(1,1,0); 
    glBegin(GL_QUADS); 
    glVertex2f(-8.7, -3.8);
    glVertex2f(-9.5, -3.8);
    glVertex2f(-9.5, -3.0);
    glVertex2f(-8.7, -3.0);
    
    // sun 
    glColor3f(1,1,0); 
    glBegin(GL_QUADS); 
    glVertex2f(-6.2, 0.8);
    glVertex2f(-7.8, 0.8);
    glVertex2f(-7.8, -0.8);
    glVertex2f(-6.2, -0.8);
    glEnd(); 
    glFlush(); 
}


void reshape(int w, int h)
{
    glViewport(0, 0, (GLsizei)w, (GLsizei)h);
    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    gluOrtho2D(-10, 10, -10, 10);
    glMatrixMode(GL_MODELVIEW);
}
