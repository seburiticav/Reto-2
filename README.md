# Reto #02 de POO
Entrega del segundo reto planteado por Felipe Gonzales Roldan para programacion orientada objetos en la Universidad Nacional de Colombia
```mermaid
classDiagram
direction LR
    class SistemaEducativoUniversitario {
	    +int estudiantes
	    +int profesores
	    +int programas
	    +int clases
	    +registrarEstudiante(estudiante)
	    +registrarProfesor(profesor)
	    +crearClase(clase)
	    +generarHistorialAcademico(estudiante)
	    +generarCertificado(estudiante)
	    +procesarGraduacion(estudiante)
    }
    class Estudiante {
	    +string nombre
	    +string programa
	    +int codigo
	    +int semestre
	    +matricularClase(clase)
	    +cancelarClase(clase)
	    +consultarNotas()
	    +calcularPromedio()
    }
    class Profesor {
	    +string nombre
	    +string especialidad
	    +asignarClase(clase)
	    +registrarNota(estudiante, evaluacion, nota)
	    +consultarEstudiantes(clase)
    }
    class Clase {
	    +string nombre
	    +int creditos
	    +string horario
	    +agregarEstudiante(estudiante)
	    +removeEstudiante(estudiante)
	    +listaEstudiantes()
	    +agregarTrabajo(evaluacion)
    }
    class Programa {
	    +string nombre
	    +string nivel
	    +agregarClase(clase)
	    +consultarPlanEstudios()
	    +verificarRequisitos(estudiante)
    }
    class Evaluacion {
	    +string porcentaje
	    +string fecha
	    +string tipo
	    +calificar(estudiante, nota)
	    +obtenerNota(estudiante)
    }

    SistemaEducativoUniversitario *-- Estudiante
    SistemaEducativoUniversitario *-- Profesor
    SistemaEducativoUniversitario *-- Clase
    SistemaEducativoUniversitario *-- Programa
    Clase --> Evaluacion : contiene
    Programa -- Clase : incluye
    Clase --> Estudiante : inscritos
    Clase --> Profesor : imparte
