# Code-Challenge
Practica 5 de la semana 4 requerimientos:

1. Habilitar un endpoint para consultar todos los estudiantes con todos sus campos.
2. Habilitar un endpoint para consultar los emails de todos los estudiantes que tengan certificación `haveCertification`.
3. Habilitar un endpoint para consultar todos los estudiantes que tengan `credits` mayor a 500.

### Dependencias Utilizadas

1. Utilización de `JTEST` para emplear los test.
2. Utilización de `express` para automatizar servidores.
3. Utilización de `linter` para correción de codigo.

### Diseño de componentes

```mermaid
graph TD;
    BD --> Reader;
    Reader --> StudentController;
    StudentController -- test --> Server;
    Server --> A{API};
    A --> v1/students/
    A --> v1/students/emails
    A --> v1/students/credits
```

### Explicación de la API

Para obtener a todos los estudiantes de la `bd.js` emple el siguente codigo en el servidor:

```JavaScript
app.get("/v1/students", (request, response) => {
  const students = getStudents();
  response.json(students);
});
```

Para obtener a todos los emails de la `bd.js` emple el siguente codigo en el servidor:

```JavaScript
app.get("/v1/students/emails", (request, response) => {
  const students = getStudents();
  const emails = getEmails(students);
  response.json(emails);
});
```

Para obtener a todos los creditos de la `bd.js` emple el siguente codigo en el servidor:

```JavaScript
app.get("/v1/students/credits", (request, response) => {
  const students = getStudents();
  const credits = getCredits(students);
  response.json(credits);
});
```