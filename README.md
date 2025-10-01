# Gestor de Usuarios - Módulo 2

## 1. Descripción del proyecto
Este proyecto consiste en el diseño de una ventana de gestión de usuarios usando **Java Swing**. El objetivo es practicar el uso de **paneles (JPanel)** y **layouts** como BorderLayout, FlowLayout, GridLayout y GridBagLayout para organizar de manera profesional la interfaz gráfica. También se implementa un **JDialog modal** de confirmación al pulsar “Guardar”.

La ventana principal se divide en varias zonas: header, menú lateral, formulario central, previsualización y botonera inferior.

---

## 2. Organización de la ventana (Wireframe explicativo)
La ventana “Gestor de usuarios” está organizada de la siguiente manera:

- **Arriba (NORTH / header):**  
  Título “Gestor de usuarios” con un icono. Se utilizó **FlowLayout** para alinear correctamente los componentes.

- **Izquierda (WEST / menú lateral):**  
  5 botones de navegación: Dashboard, Usuarios, Informes, Ajustes, Ayuda. Se utilizó **GridLayout 5x1** para que los botones tengan el mismo tamaño y estén distribuidos uniformemente.

- **Centro (CENTER / formulario):**  
  Formulario con campos: Nombre, Email, Rol (ComboBox), Activo (CheckBox) y Notas (TextArea dentro de JScrollPane). Se utilizó **GridBagLayout** para que los campos crezcan correctamente al redimensionar la ventana y estén alineados.

- **Derecha (EAST / previsualización):**  
  Panel con **BorderLayout** conteniendo un `JTabbedPane` con pestañas “Resumen” y “Logs”. Se fijó un **PreferredSize** para que el panel no ocupe todo el ancho disponible.

- **Abajo (SOUTH / botonera):**  
  Botones “Cancelar”, “Limpiar” y “Guardar”, usando **FlowLayout RIGHT** para alinearlos a la derecha.

---

## 3. Árbol de contenedores
JFrame (BorderLayout)
├─ NORTH: headerPanel (FlowLayout)
├─ WEST: navPanel (GridLayout 5x1)
├─ CENTER: formPanel (GridBagLayout)
├─ EAST: previewPanel (BorderLayout → JTabbedPane)
└─ SOUTH: buttonBar (FlowLayout RIGHT)

**Justificación de layouts:**

- **BorderLayout:** divide la ventana en zonas principales.  
- **FlowLayout:** header y botonera, permite alineación flexible.  
- **GridLayout:** panel de navegación, asegura que los botones tengan tamaño uniforme.  
- **GridBagLayout:** formulario central, campos alineados y escalables al redimensionar.  
- **BorderLayout en previewPanel:** mantiene tamaño del `JTabbedPane` y organiza su contenido.

---

## 4. Propiedades clave de paneles y campos

| Panel / Campo | Layout | Propiedades clave |
|---------------|--------|-----------------|
| navPanel      | GridLayout(5,1) | vgap=5, botones mismos tamaños |
| formPanel     | GridBagLayout    | insets=5, weightx=1 en campos, weighty=1 en Notas, fill HORIZONTAL/BOTH |
| previewPanel  | BorderLayout     | PreferredSize width=260px |
| buttonBar     | FlowLayout(RIGHT)| Botones alineados a la derecha, default=Guardar |

---

## 5. Explicación RA1 y RA4

**RA1 (Diseño de interfaces):**  
Se eligieron distintos layouts para cada zona de la ventana, logrando una interfaz clara, ordenada y flexible. Los campos del formulario crecen horizontal y verticalmente al redimensionar, mientras que los paneles laterales y la botonera mantienen su tamaño y alineación, garantizando buena usabilidad.

**RA4 (Uso de herramientas de desarrollo):**  
Se utilizó **IntelliJ GUI Designer** y programación en Java Swing para crear paneles, configurar layouts y ajustar propiedades como insets, weightx/weighty, fill y preferredSize. También se implementó un **JDialog modal** para confirmación de cambios.

---

## 6. Instrucciones de ejecución

1. Abrir el proyecto en **IntelliJ IDEA**.  
2. Ejecutar `GestorUsuarios.main()`.  
3. Redimensionar la ventana para verificar que los campos y el área “Notas” crecen correctamente.  
4. Pulsar **Guardar** para abrir el diálogo modal.  
5. Verificar que los paneles laterales y la botonera se mantienen alineados correctamente.

---

## 7. Estructura de entrega sugerida
GestorUsuarios/
├─ src/
│ ├─ GestorUsuarios.java
│ └─ DialogConfirmacion.java
├─ README.md
└─ Tarea Modulo 2.pdf (PDF con wireframe y capturas de pantalla)
