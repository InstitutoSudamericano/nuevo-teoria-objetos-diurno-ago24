# CRUD
# ¿Qué es CRUD?

CRUD representa las cuatro funciones que se usan para administrar los datos que se guardan en las aplicaciones de bases de datos. La función "crear" permite que se generen nuevos registros en las bases de datos. "Recuperar" da a la capacidad de buscar y leer los datos. "Actualizar" se refiere a la modificación de los registros que ya figuran en ella. "Eliminar" permite borrar la información innecesaria de una base de datos. El método CRUD se basa en el almacenamiento continuo. Si se corta la energía, los datos permanecen en el disco duro o la unidad.

![CRUD](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAkGBxIQDxUQEg8VFRUVFQ8VFRUVFRUVFRUVFRUWFhUVFRUYHSggGBolHRUVITEhJSkrLi4uFx8zODMtNygtLisBCgoKDg0OGxAQGy0lHyUuKy81LS0tLi0yLS0tLS0tLS0vLy0rLS8tLS0vLS0tLS0tLS0tLSstLS0tLS0tLS0tL//AABEIAKgBKwMBEQACEQEDEQH/xAAaAAEBAAMBAQAAAAAAAAAAAAAAAQIEBQMG/8QARRAAAgECAwMHBwgIBgMAAAAAAAECAxEEEiEFMUEGExVRYWOTIjJCU3GBkRQzNHKSobGyI1Jzg7PBwtE1YoK00vAWJOH/xAAbAQEAAwEBAQEAAAAAAAAAAAAAAgMEAQYFB//EADgRAQACAQEDCAgGAgIDAAAAAAABAgMREiGSBBQVMUFRU2ITIjJhgZGx8AUzUnGh4TTRQsEjsvH/2gAMAwEAAhEDEQA/AMmfTfHAIwAFAoEAAQCgAKBADAgFAoACAGBAKgKAAgEYBAVAUAwJcCMABUBQIwAEAoEYAAAAoACAAAFAAAIAAAUAwAEAAAKAAAQAAAoACMAAAICgAIwAAAAAAAAABYAAAAAACwAAAAIAAsAAALgEAYCwAAAAAGAsAAAAAAAAsAAWAoEAqQEsAAWAMAAsAsAsAsAAAWwEsAsBUgIwFgK0BLALALAAFgLYCALAWwEAJALAAFgK2AsAAAAKB7YHBzr1FSpxvKW5cO1t8EjlrRWNZSrWbTpD6aryfwWGtHFYuWfRuNNbr9aUZP3uxRGS9vZhonFjp7c7z/xnD4iDlgsU5SWrhU3/AIJx9rTHpbVn14PQ0tHqS+Vq03CTjJNSi2mnvTW9GjXVmmNN0sA4oEA3ti4FYjEU6MpNKbabW9Wi3x9hG9tmsynjrtWiH0OK5O4GlN0546UZRtdPLdXSa4dTRTGXJMaxVfOHFE6TZjR5M4Ss8lDHpz1smou9uzRsTlvG+akYcdt1bPnNpYCeHqypVF5Uerc09zT6mX1tFo1hnvWazpLVOogCwGxs7DqrWp022lOdODa3pSkldfE5adImUqxraIbnKPZkcLiOajJyWWMrytfW/URx32q6pZaRS2kOYTVu3tzYkcPh6FaM5N1VFtO1leClpb2lVMk2tMdy7JiitYnvcNFqksAAoH1lHkzhlhqVetiZU+cjB+jbNKOay07H8DPOW21MRDVGGmzFrTpqxXJ/Az8mntFZnuzZf/h30l466ueixz1WcjbmwauEks9nGXmzj5rfU+p9n4llMkX6lWTFanW5ZNWAUABLgAAFAAYsCoCgAPseRqVDCYnGWTlFSjG/+WKlb3tx+CM2b1rRVrwerS13yFWo5ScpNuUm2297b3s0xuZJnXre+y8fLD1o1ob4vdwkno4vsI2rtRpKVLTW2sM9r7Q+U1pVsig5ZbpO6ula/wByFK7MaO5L7dtWmSQAIB2OSP0+h9af5JFeX2JW4PzIenLGlJ4+s1GTV6e5P1cDmGY2IdzxPpJeGwNnVqmJpOFOSyzhJys0oqMk22/YmdyWrFZ1cxUtNo0hvcvcRGeMtF3yQhCVv1rybXuzIjgjSifKZib7nzpczgEYG7sL6XQ/bUPzojf2ZTx+3H7w63L36a/2dP8AmV4PYWcp9t86XKH2HLD6Dg/qw/hRM+H27Nef8uv32PjzQyIwIBQPseUn+E4P9x/BmZ8f5tvvta8v5Nfh9Hx7NDI+12LUeK2VXpTd3SUsje9KMc8Nexpr2aGa8bOSJjtbMc7eKYnsfEXNLGICgUAwAGIFYACMABQKB9nyWjz2zcTQjrPy2lxeaCy/FxaM2XdkiWvD62O1XxdzSyPfZ2EdatCinZzko3teye9242V37jlrbMapVrtWiGzt3Ziwtd0ecz2UW3ly2b1ta74W+JGl9qNXclNi2mrn3JoKBLgdfkj9PofWn/DkV5fYlbg/Mh3+UXKzEYfFVKMFTyxyWzRk3rCMndqXW2VY8NbViZX5c9q2mITYnLCrWrxo1owy1HkvDNGSb0XHrsuG8XwREawY+UTa2lu189ylwCw+KnTjfLpKN3d2kr2vxs7r3F2O21XVny02bzEOYTVpcAwNzYbti6H7ah+eJG/sz+yeP24/eHY5fxtjb9dOm18ZL+RXg9hbyn23zbZczvsuWay4PCRe9Rjp7KcUzPh9uzXn3UrD425oZEYBAVAfY8pP8Jwf7j+DMz4/zbffa15fya/D6PjjQyPs+TcXR2Xia0tFNTUb8fJyL4yk17jNk35IhrxeritZ8WaWQAqAAGAuBAKBGwAAABbgdHYO2JYStzkVdNWnHdmj/JrgyGSkXjRZjyTSdXfxeH2bi5OrHE8xKWsoysld73Z6X9jsVROSm7TVfNcV9+ujLC4nAbPTnSqPEVrNRfBX6na0V26s5MZMm6d0ETjxb43y+SxmJlVqSqTd5Sbk3/bs4e40RERGkMtrTadZeR1wAAdHk3ioUsXSqVJZYxcm3q7XhJcO1ohkiZrMQsxTFbxMsuU+KhWxlWpTlmjJws7NXtTino9d6YxxMViJMtoteZhpYCqoVqc3ujOnJ+xSTf4ErRrEwjWdLRLs8s8ZSrYhVaNRTTgk7KSs4t9aXBr4FeGs1rpK3PatraxLgFqgAgFjJppp2aaafU1uYH2dTauD2hTjHEydGrFWzrc+uzs1Z77Pdw6zNFL459XfDXt48setul5UNmbOoyVSpjFVS1UFZptdajdv7js3yTuiNHIphrvm2rk8p9t/LKykk4wgmoJ79d8n2uy07EWYsexCrNk25ce5YqQAAA+3+W4GvgqFCtiXB040m1FSupRg4tN5WuLM2zkreZiGzax2xxW09TUhhdkweZ4irUt6NpWf2YJ/eS1yz2IbOCO3Vpco+UfyiMaNKHN0Y2tHROVt10tElwX/AFSx4tmdZ60cubajZjdDgFqgAICgAIwAAAAAAGAAoEAAADAIAAAAAABAGAsAAALgEgAAAAAAADAAAAAAAAAWwEsBbAAJYDcpYDNFPnqKuk7Ook1fg1wZgv8AiEUtNfRZJ07YpMx8J7mivJ9YidqvEy6N7+h4qIdJR4WXgl3m3nrxHRvf0PFR3pKPCy8EnNvPTiOje/oeKjnSUeFl4JObeenEdG9/Q8VDpKPCy8EnNvPTiTo1+voeKh0lHhZeCTm3npxL0b39DxUOko8LLwSc289OI6N7+h4qHSUeFl4JObeenEdG9/Q8VDpKPCy8EnNvPTiOje/oeKh0lHhZeCTm3nrxD2a/X0PFQ6SjwsvBJzbz14k6N7+h4qHSUeFl4JObeenEvRvf0PFQ6SjwsvBJzbz04jo3v6HiodJR4WXgk5t56cR0b39DxUOko8LLwSc289OIWze/oeKh0lHhZeCTm3nrxD2a/X0PFQ6SjwsvBJzbz04jo3v6HiodJR4WXgk5t56cR0b39DxUOko8LLwSc289OI6Nfr6HiodJR4WXgk5t56cR0b39DxUOko8LLwSc289OIWze/oeKh0lHhZeCTm3npxHRr9fQ8VDpKPCy8EnNvPTiOje/oeKh0lHhZeCTm3npxHRr9fQ8VDpKPCy8EnNvPTiTo3v6HiodJR4WXgk5t56cS9G9/Q8VDpKPCy8EnNvPTiaco2bV07Nq61T7UfRrbarE9/ezzGk6MbHXFSAWAlgLYAAAAAAFAgCwAABQAEAAAAFAgAAAAAUCMAgAAABQIwCAAAKAAjAIABQAGLAqAqAAbmCjSa8vL52uZzTUbaZMu93ve/Z2kba9iddntbcoYVxTTS18rz8yipeinJ6tLt3rdwj66elNGK+TNuyja0nG7qJ3bpuMX5drpOov9Pxes56n38P7cksVKAAAGB1KccM4cMygt7mk5Wp39LXXnOr2PQrna1WxsaLKnhraSTsknfOpXjGacoJOzzPm2r9b0Q1uaUcosVAACMCAdWaw0Yy9JucsqTnpBqWXW6s01G97+zqhG0tnYh6VIYVOWqv5WVRdRwVpSacm3fWKiuOr4HNbuzFGvj1RyJ01FPNO9nNuylNR86T9FRe47XXXejbZ03NAmrRgRAUDpbPhQajzuXz3m1nmteGWyWlvPvx+4hba7FlYr2vSNKhmu3C2WWl5+fmdvS3Ze05rZ3SurD9C6b8mCkoxtrU87y72vK3CHxO+tq56ujlsmrEBUBQAADG4FYACMABQABgAIAAoFAgACAEBQKBAAEAqAAUCAQAgKgAGPOLrI7dUti3cqZKJ1cmNOsYcAKAAMABAABsAAAAY1KiiryaS627IJVra06VjV49IUvWw+0gs5tm/TPyPl9L1sPtIHNs36Z+TOvXy2STlKTtGK3yfZ2dpy1orG1bqd5Pye+a+zVhiqFTDqM6k1PO0pQW+Mnu5v9ZLj8TFyflsZrzWI+/e+vyr8MpTFE1nSYbJufBAAE9wAAkBbMCAW4EuAAqVxMxHW5NorGsyNNFcZaTbZ1U15RjtbZif7CxegC4ADKEbsja2zGqVa7U6PTme0r9LPcs9FDFYZEIvpHUnNdZ61jQsrXO1yaRo5bHrOrGpCxbS+0qvTZYE0ACgQA2AuAAAAAADTrRUq8E1dKFSST3XvFXDTjma4LTHfEfVtc3H9VfBBRt273hi6kacHNwT6kkrtvchO5bhrfLeKxLbwvN4en8pqSVSpUSy5db33U6XZ1v4nw818vKsvo6xpEfesvU4cWLkuLVrxjKc+dq6z4L0acf1Y9vW+J9bBgrhrs1/+vPct5bbPbSPZezLmAQHK5Q4t06Tgl85DEq97OOWjOd18CGSdI+f0WYq6zr+31anR9KMY2wEql4QblGVNK7WvnVE/uI7MfpT27TPtffyYSw+XWjha1ColJwkmpU5NJvJUjCclZ2tquOjuc07o0d1165iYIUc6Uq2FrVqklGUrtQp08yUlTpqc4rRNJtJ6p3dxpr1xMkzp7MxEPWls+jJtPZ8oK0vKlKm0rL/AC1G/uOxWP0oze0f8vv5Njk3iXOjCDXmUcLre7eemnqSxzrHycyxpbX3y6xNUAZ0oZn2LeV5MmxHvUcoz+irujWZ3RDOVa2kdF97IVw67775U05Jtetmnan+IeUpX3k4w0i21ELqcmx1ttRH9PSnFSVuPB9ZDJa1J2uuFWe+TDb0nXXtju98PJl8Trva4mJjWAOgGUJWZG1dYSpOktqx8Hn9u6Hrug8X65/gsOf27oOhMX6p/gsOf27oOhMX6p/hr15a2Pr8ktt44vPb/t5z8QxRhz2xRviNP5iJeZpYgAAAAALYCAUAAsBqTX/sR/Z1PzRDRX8i37x9JbdgzvGTqRq0qlNwvTk5LOnJZrWi8q32u3v32K82KMtJpbqlq5Lnpi1mY1lhh8Goyc280m5Pcoxjmd5ZILSKfYSpSKxpByjld8sbPVHcmzZN07t38qpv19NkkeUxEZNI7o+kNmwZ1sBweVfmw+rjP9tUKsv+/ouw9vw+rV2nzGaHOfJM3N0vnlJztbse45bZ7dPinTa36a/BhgXSU/0Tw11Gq/0FScJryHq6e6ot3s3nK6a7tPgW2tN+vxedd0mqbrPD3dHDu+IqznJ/o46qnugt+vF3YnTt0+Lsa79nXt6obOx1Q539H8kzZZ/MqWe1uF3uO12dd2iN9rTfr8WzyVXkfucD/BRLF1fJHN1/Gfq7tixSAeu6HtZR15v2hi02+V7/APjH1YKk2rlk5KxaKz1r7copXJGOZ3y2cLg7rNPSP4/2RTlz6Ts03yzco5XszsY99vv+XjWcc94buBbStpppfracdbTj2cvXPWmJXle2zI8nn1NO5TyG0zh0nsmYeaLmwAWEux1txHkYfpUvoKvJmU5Qlhp85Sqem98OvOvj+Ht0zyeZ0mm+JfNr+IRWLRmjS0dnf+3373L2vh6dKq4UqjnFJJydvO9JK29FOSta20rOrXye9702rxpP/TlVvOfu/A9ByD/Hr8frLxv4x/mX+H0hga3zUsBUgFgIBQABAAAADUqfSIfs6n5ohor/AI9v3j6S2wzqBANTZXzX+qp+diGnlX5nwj6Q2wzAHB5VebD6uM/21Qqy/wC/ouw9vw+rPEuraGR4q3N0/mVhnDd3jzXE69mv8Eab9dPjq8FKpfy3iLZatlXpUZK+SXm1KXzb7Xo93E5v7dfilu7NPhM/9vPDzqZIKDxHzWHvzFGkl81Dzqlbz39XduEa6btfh/ZOmu/Tt65n/pu4CVXP5bxeXLK/OrDKG7u/KuSrrrv1/hC2mm7T4apyby2eS+XmsFlzWzW5rS9tL2GP3e53L7/f9XaLFIB6w1g1xWpnvOxli3ZO5hyz6LlFbz1WjT49iUauX2Es2L0ke9ZyrksZo7phnXxLno3p1f3GLDGOPecm5LXDHfPe8oQu7E8l4pXWVufLGKk2n7la0ryZHDXZpESr5JjnHiiJ6+v5sGWtIBRLsdbbR5F+lS+pht6jhVGhQhzlPfWm7p1HJWeVP+fVbtNfpqY9K13x2vkzyPLn1yZZ0t2R3ff9+5wtrU6Mar5iblTaTV01lb3x132M+SKxb1Opv5PbLNP/ACxpP3vcqtvfuPQcg/x6/H6y8b+Mf5l/h/6wwNb5oBQIAQC4FYADFgUCoDWxNGWaNSFs0VJNSuk4u3FbnoF+K9dmaX6p7u+GPOV/V0/tv/iHdnB+qfl/ac5X9XT+2/8AiDZwfqn5R/tHUr+rp/bb/pDuzg/VPyj/AG9sJRyQUb3erb6222/xCrNk9JebPcKwDmbawM6uTIoPK6maM3KKlGdOUGrxTa84hesz1LMdojXVzlsqutLaJaJY7FL+lkNi33Mp7dfuIedejioRapwrXcWrOrTr0m3dWbqONRe2/uExeOr/AG7E0md+ny0/owuHxTpxhOFa8YxhaNWlQpLKklaUHKpLdv09iERbTSdfoWmmusafX+nq9lYh8LLqeOxT/pQ2Lfcyekr9xDo7GwU6WbMoRTVKMYwlKSUaccqu5JNsnSsx1q72iep0SasbAQlZ3RG1YtGkoZMdclZrbqZVJXd7WIxE0p3q6Vthx6TM20+9GUIpq7lbs4lNM97RuqzU5VltHq01/iFlUSVo+98SdcdrTtX+SynJ73tF809XVEdUPNF7YxYBAVB2G2meTvSaTs2636NjyVyVi9J1iQimAatV6s9LyOk0wVi3X/bwn4nkrk5Ve1Z1jd/ERDFGlgVAUAwAGNwKAAjAAUAAAARgAKBQIAuBAAFAAAAEAXAoNAABACAqAAGAAjAAVMAAAAQAAbAXAAAAABcAAAAAAC4AAAAAAFwAAAAAMBcAAAAADAXAMAAAAGAAXAAAAAAAuAAAAABAAAACgQAgDAAEAuBAKAAAEAAgFAAACAAEAuAAAf/Z)

# Ventajas de CRUD

El patrón de Casos de Uso CRUD ofrece varias ventajas:

**Centralización de acciones básicas:** El patrón CRUD permite reunir en un solo elemento de configuración del software todas las acciones básicas que se realizan sobre una entidad de dominio. Esto facilita la gestión y el mantenimiento del código.

**Facilidad de comprensión:** Al utilizar el patrón CRUD, se logra una mayor comprensión por parte del cliente sobre la funcionalidad del sistema. Esto se debe a que las acciones básicas (Crear, Leer, Actualizar, Eliminar) son intuitivas y fáciles de entender.

**Especificación detallada:** El patrón CRUD facilita la especificación de los casos de uso al lograr un alto nivel de detalle sin tener que invertir esfuerzo en describir aspectos generales de 
funcionalidad más de una vez. Esto ahorra tiempo y evita la redundancia en la documentación.

**Reusabilidad del código:** Al identificar relaciones entre los Casos de Uso, el patrón CRUD facilita la reutilización del código con un mínimo esfuerzo. Esto significa que se pueden aprovechar las implementaciones existentes para acciones similares en diferentes entidades de dominio, lo que ahorra tiempo y recursos en el desarrollo.

# Desventajas de CRUD

La principal desventaja es que si no se cuenta con una métrica completa para estimar la complejidad de los Casos de Uso y la planificación del proyecto se basa únicamente en el nivel del Caso de Uso como unidad, es muy probable que el proyecto sufra retrasos y exceda su presupuesto en comparación con otros proyectos que no utilicen este patrón


# CRUD en PRISMA

El CRUD actúa como operaciones básicas de creación, lectura, actualización y eliminación de datos en una base de datos utilizando Prisma Client. Prisma Client es un generador de consultas de base de datos autogenerado y seguro en cuanto a tipos que se utiliza para enviar consultas a la base de datos. 
CRUD en Prisma utilizando Prisma Client:

`import { PrismaClient } from '@prisma/client';

`const prisma = new PrismaClient();

`// Crear un nuevo registro
`const createUser = await prisma.user.create({
  `data: {
    `email: 'fernando@gmail.com',
    `name: 'fernando',
  `},
`});

`// Leer un registro por identificador único
`const userByEmail = await prisma.user.findUnique({
  `where: {
    `email: 'fernando@gmail.com',
  `},
`});

`// Leer un registro por ID
`const userById = await prisma.user.findUnique({
  `where: {
    `id: 3,
  `},
`});

`// Actualizar un registro
`const updateUser = await prisma.user.update({
  `where: {
    `id: 5,
  `},
  `data: {
    `name: 'fernando5',
  `},
`});

`// Eliminar un registro
`const deleteUser = await prisma.user.delete({
  `where: {
    `id: 4,
  `},
`});

**Se utiliza métodos proporcionados por Prisma Client, como `create`, `findUnique`, `update` y `delete`**


# CRUD en TypeORM

El CRUD se implementa utilizando los métodos proporcionados por TypeORM para interactuar con la base de datos.

* Se define utilizando una clase en TypeScript o JavaScript y se mapea a una tabla en la base de datos. La entidad define las propiedades y relaciones de los registros en la tabla. 

* Se crea un repositorio en el cual es una clase que se encarga de realizar las operaciones CRUD (Crear, Leer, Actualizar, Eliminar) en la base de datos para una entidad específica. El repositorio se crea utilizando la clase de la entidad y se configura para interactuar con la base de datos. 

* Se utilizan los métodos proporcionados por TypeORM para realizar las operaciones CRUD en la base de datos. Estos métodos incluyen crear un nuevo registro, leer registros existentes, actualizar registros y eliminar registros..

CRUD en TypeORM utilizando TypeScript:

`import { Entity, Column, PrimaryGeneratedColumn, Repository } from 'typeorm';

`@Entity()
`class User {
  `@PrimaryGeneratedColumn()
  `id: number;

  `@Column()
  `name: string;

  `@Column()
  `email: string;
`}

`// Crear un nuevo usuario
`const createUser = async (userRepository: Repository<User>) => {
  `const user = new User();
  `user.name = 'Fernando E';
  `user.email = 'fernando@gmail.com';

  `await userRepository.save(user);
`};

`// Leer usuarios existentes
`const getUsers = async (userRepository: Repository<User>) => {
 ` const users = await userRepository.find();
  `console.log(users);
`};

`// Actualizar un usuario existente
`const updateUser = async (userRepository: Repository<User>) => {
  `const user = await userRepository.findOne({ id: 1 });
  `if (user) {
    `user.name = 'fernando2';
    `await userRepository.save(user);
  `}
`};

`// Eliminar un usuario existente
`const deleteUser = async (userRepository: Repository<User>) => {
  `const user = await userRepository.findOne({ id: 1 });
  `if (user) {
    `await userRepository.remove(user);
  `}
`};

Se define una entidad User con las propiedades id, name y email. Luego, se utilizan los métodos del repositorio para crear un nuevo usuario, leer usuarios existentes, actualizar un usuario y eliminar un usuario.


# Conclusion

Prisma es un ORM ligero y completamente seguro para Node.js y TypeScript. Utiliza un esquema declarativo para definir los modelos de la aplicación y genera migraciones SQL a partir de ese esquema. Prisma Client proporciona consultas CRUD completamente seguras y tipadas para interactuar con la base de datos.

TypeORM es un ORM tradicional que mapea tablas a clases de modelo. Estas clases de modelo se utilizan para generar migraciones SQL y proporcionan una interfaz para consultas CRUD en tiempo de ejecución. TypeORM se acerca más a SQL en su API y proporciona un generador de consultas que permite construir consultas de base de datos de manera programática.

**Prisma como TypeORM son excelentes opciones para implementar operaciones de CRUD en aplicaciones. Ambas ofrecen eficiencia, seguridad y facilidad de uso. Sin embargo, la elección entre ellas dependerá de las necesidades específicas del proyecto.**