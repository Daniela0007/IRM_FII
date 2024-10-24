# IRM

## Demo Video: [Demo Video](https://we.tl/t-vIhYy67JD6)

**Modelul Mâinii și Animația:**
- Modelul mâinii a fost creat și animat pentru *GrabMotion* direct în **Blender**, modelul se afla in proiectul ZIP.

#### **Scriptul HandController**:
- gestionează input-urile din **XR Action-Based Controller** (atașat la ambele controllere de mâini).
- preia acțiunile de intrare (*G* - actiunea de Grab, *Hold Left Mouse Button* - actiunea de Trigger) și setează valorile corespunzătoare pentru parametrii **Grab** și **Trigger** în clasa `Hand`.

#### **Scriptul Hand**:
- gestionează stările animațiilor mâinii pentru acțiunile de **Grab** și **Trigger**.
- setează valorile țintă pentru **Grab** și **Trigger** pe baza inputurilor de la controller.
- la fiecare frame, metoda **AnimateHand()** verifică dacă **currentGrab** este diferit de **grabTarget** (indicând o stare activă de apucare) și folosește funcția **Mathf.MoveTowards()** pentru a aduce treptat 
  **currentGrab** mai aproape de valoarea țintă. Pe măsură ce se apropie de **grabTarget**, mâna trece lin de la deschisă la închisă (sau invers), controlând animația prin parametrul 
  Grab din HandAnimator. La fel pentru animatia de Trigger.

#### **Animații:**
- În folderul **Animation**, avem un **HandAnimator** cu două layere:
    - Un layer pentru **Trigger**.
    - Un layer pentru **Grab**.
    - Fiecare layer are parametrii `float` **Trigger** și **Grab** pentru a controla animațiile respective.
- Am folosit **BlendTree** pentru o tranziție lină între starea **Idle** și acțiunile de **Grab/Trigger**.

 **Avatare:**
- Am folosit două avatare diferite:
    - un avatar pentru animația de **Grab**.
    - un avatar pentru animația de **Trigger**.
    - ambele sunt derivate din **HandGrabbingAnimation** si avatarul **Trigger** să includă doar **thumb bones** și **index bones**

## Arhiva Proiect:
[Proiect ZIP](https://we.tl/t-Z2OObznmYA)

