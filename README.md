# Zustand Task Manager

<div align="center">
  <img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="React" />
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Zustand-000000?style=for-the-badge&logo=npm&logoColor=white" alt="Zustand" />
  <img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white" alt="Vite" />
</div>

## 📋 Índice

- [Descripción](#-descripción)
- [Características](#-características)
- [Tecnologías](#-tecnologías)
- [Instalación](#-instalación)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Gestión de Estado con Zustand](#-gestión-de-estado-con-zustand)
- [API Mock](#-api-mock)
- [Contribuir](#-contribuir)
- [Licencia](#-licencia)

## 🔍 Descripción

Task Manager es una aplicación moderna para la gestión de tareas desarrollada con React y TypeScript, utilizando Zustand como gestor de estado. Esta aplicación demuestra cómo implementar un flujo de trabajo eficiente y mantenible para aplicaciones frontend.

## ✨ Características

- **Gestión Completa de Tareas**: Crear, leer, actualizar y eliminar tareas
- **Interfaz Intuitiva**: Diseño limpio y amigable para el usuario
- **Validación de Formularios**: Previene la entrada de datos incorrectos
- **Alertas Interactivas**: Notificaciones informativas durante las operaciones
- **Persistencia de Datos**: Almacenamiento local mediante JSON Server

## 🛠️ Tecnologías

### Frontend
- **React**: Biblioteca para construir interfaces de usuario
- **TypeScript**: Superset de JavaScript con tipado estático
- **Zustand**: Gestor de estado minimalista y poderoso
- **CSS Modules**: Estilos encapsulados por componente

### Herramientas
- **Vite**: Bundler y entorno de desarrollo
- **Axios**: Cliente HTTP para peticiones a la API
- **SweetAlert2**: Bibliotecas de alertas personalizadas
- **JSON Server**: API REST mock para desarrollo

## 📥 Instalación

1. **Clonar el repositorio**
   ```bash
   git clone https://github.com/tu-usuario/zustand-task-manager.git
   cd zustand-task-manager
   ```

2. **Instalar dependencias**
   ```bash
   npm install
   ```

3. **Iniciar servidor de desarrollo**
   ```bash
   npm run dev
   ```

4. **Iniciar JSON Server (en otra terminal)**
   ```bash
   npm run dbDev
   ```

## 📁 Estructura del Proyecto

```
src/
├── components/
│   ├── ui/
│   │   ├── CardList/
│   │   ├── Header/
│   │   ├── ListTareas/
│   │   └── Modal/
│   └── ...
├── hooks/
│   └── useTareas.ts
├── models/
│   └── tarea.model.ts
├── services/
│   └── tareas.service.ts
├── store/
│   └── tareas.store.ts
└── ...
```

## 🧠 Gestión de Estado con Zustand

Zustand ofrece varias ventajas frente a otras soluciones de estado:

- **Simplicidad**: API mínima y fácil de entender
- **Rendimiento**: Actualización selectiva de componentes
- **Flexibilidad**: Integración sencilla con otras herramientas
- **TypeScript**: Soporte nativo para tipos

Ejemplo de implementación:

```typescript
import { create } from 'zustand';
import { Tarea } from '../models/tarea.model';

interface TareasState {
  tareas: Tarea[];
  isLoading: boolean;
  fetchTareas: () => Promise<void>;
  addTarea: (tarea: Tarea) => Promise<void>;
  // Otras acciones...
}

export const useTareasStore = create<TareasState>((set) => ({
  tareas: [],
  isLoading: false,
  fetchTareas: async () => {
    set({ isLoading: true });
    // Lógica para obtener tareas
    set({ isLoading: false, tareas: /* resultado */ });
  },
  // Implementación de otras acciones...
}));
```

## 🌐 API Mock

El proyecto utiliza JSON Server para simular una API REST:

- **Endpoint**: `http://localhost:3000/tareas`
- **Métodos**: GET, POST, PUT, DELETE
- **Estructura de datos**: Ver `db.json`

## 🤝 Contribuir

Las contribuciones son bienvenidas. Para contribuir:

1. Haz fork del repositorio
2. Crea una rama para tu feature (`git checkout -b feature/amazing-feature`)
3. Haz commit de tus cambios (`git commit -m 'Add some amazing feature'`)
4. Empuja a la rama (`git push origin feature/amazing-feature`)
5. Abre un Pull Request

## 📄 Licencia

Distribuido bajo la licencia MIT. Ver `LICENSE` para más información.
