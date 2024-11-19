**№1. Pregătirea lucrării**

1. **Crearea unui proiect nou Laravel**:
   1. Comandă: laravel new task-manager sau composer create-project laravel/laravel task-manager.
1. **Configurarea fișierului .env**:

   ![](Aspose.Words.b4cd970f-b785-4751-9b05-de8de8ff567d.001.png)
#### **№2. Crearea formularului**
1. **Crearea formularului HTML cu șabloane Blade**:
   1. Vizualizare: resources/views/tasks/create.blade.php

![](Aspose.Words.b4cd970f-b785-4751-9b05-de8de8ff567d.002.png)

**Controllerul TaskController**:

![](Aspose.Words.b4cd970f-b785-4751-9b05-de8de8ff567d.003.png)

**Crearea rutei**:

- În routes/web.php

  ![](Aspose.Words.b4cd970f-b785-4751-9b05-de8de8ff567d.004.png)
#### **№3. Validarea datelor pe partea de server**
Validarea este implementată în metoda store, cu reguli specifice pentru fiecare câmp.

**1. Metoda store cu validare directă**

![](Aspose.Words.b4cd970f-b785-4751-9b05-de8de8ff567d.005.png)
#### **2. Afișarea erorilor de validare în formular**
În fișierul Blade unde se află formularul (resources/views/tasks/create.blade.php)

![](Aspose.Words.b4cd970f-b785-4751-9b05-de8de8ff567d.006.png)
#### **№4. Crearea unei clase de cerere personalizată**
1. **Crearea clasei CreateTaskRequest**:
   1. Comandă: php artisan make:request CreateTaskRequest.
1. **Definirea regulilor în CreateTaskRequest**:

![](Aspose.Words.b4cd970f-b785-4751-9b05-de8de8ff567d.007.png)

1. **Actualizarea metodei store**:

![](Aspose.Words.b4cd970f-b785-4751-9b05-de8de8ff567d.008.png)

#### **№5. Adăugarea mesajelor flash**
- În create.blade.php

![](Aspose.Words.b4cd970f-b785-4751-9b05-de8de8ff567d.009.png)
####
####
#### **№6. Protecția împotriva CSRF**
Directiva @csrf este deja adăugată în formularul HTML.

![](Aspose.Words.b4cd970f-b785-4751-9b05-de8de8ff567d.010.png)
#### **№7. Actualizarea sarcinii**
1. **Crearea metodei edit**:

![](Aspose.Words.b4cd970f-b785-4751-9b05-de8de8ff567d.011.png)

1. **Crearea metodei update**:

![](Aspose.Words.b4cd970f-b785-4751-9b05-de8de8ff567d.012.png)

1. **Rutele pentru editare**:

![](Aspose.Words.b4cd970f-b785-4751-9b05-de8de8ff567d.013.png)
1. #### ` `**Formular pentru editare**
Creați resources/views/tasks/edit.blade.php

![](Aspose.Words.b4cd970f-b785-4751-9b05-de8de8ff567d.014.png)

**Întrebări de control**

1. **Ce este validarea datelor?** Este procesul de verificare a corectitudinii și conformității datelor primite de la utilizator pentru a preveni erori și vulnerabilități.
1. **Cum se protejează formularele împotriva CSRF?** Laravel folosește token-uri unice (@csrf) pentru fiecare sesiune, prevenind cererile neautorizate.
1. **Cum se creează clase de cerere personalizată?** Se folosește comanda Artisan php artisan make:request NumeRequest. Regulile și mesajele sunt definite în metodele rules și messages.
1. **Cum se protejează datele împotriva atacurilor XSS?** Laravel scapează automat datele afișate în vizualizări folosind directiva {{ $variable }} pentru a preveni injecțiile de cod malițios.

