# Cours 1 : Du DOM JavaScript à Vue 3 (Composition API)  
_Horaires : 09 h 30 → 12 h 30_

---

## 0. Objectifs de la matinée
1. Comprendre **le DOM** et le manipuler en JavaScript « vanilla ».
2. Identifier les **limites** du DOM manuel.
3. Découvrir **Vue 3** et sa **Composition API** (`ref`, `reactive`, `computed`, `watch`).
4. Écrire un **premier composant réactif**.
5. Préparer le terrain pour **Nuxt 3** (cours de l’après-midi).

---

## 1. Kick-off (09 h 30 → 09 h 45)

### 1.1 Matériel indispensable
| Outil | Rôle | Vérif ✓/✗ |
|-------|------|-----------|
| **Navigateur** (Chrome / Firefox) | Exécuter le code & DevTools |   |
| **CodePen** | Partager des snippets live |   |
| **Node ≥ 18** | (utilisé l’après-midi) |   |

> **Astuce CodePen**  
> _Settings → JavaScript → ✚ Add External Scripts_  
> Ajoutez : `https://unpkg.com/vue@3/dist/vue.global.js` (charge Vue 3 en CDN).

### 1.2 Cloner le repo (si connexion GitHub)
```bash
git clone https://github.com/votre-org/pokedex-nuxt-workshop.git
cd pokedex-nuxt-workshop

## 2. DOM JavaScript « vanilla » (09 h 45 → 10 h 15)

### 2.1 Qu’est-ce que le **DOM ?**
> **Document Object Model**  
> Le navigateur lit votre HTML et construit un **arbre d’objets**.  
> Chaque balise devient un *node*, chaque attribut une propriété JavaScript.

| Opération | API JavaScript | Exemple |
|-----------|---------------|---------|
| Sélection | `document.querySelector()` | `const btn = document.querySelector('#btn')` |
| Lecture   | `.innerText` / `.innerHTML` | `console.log(btn.innerText)` |
| Écriture  | idem | `btn.innerText = 'Nouveau texte'` |
| Écouteur  | `addEventListener()` | `btn.addEventListener('click', fn)` |

---

### 2.2 Exemple minimal : changer du texte
```html
<!-- Copiez/collez dans CodePen -->
<button id="btn">Clique !</button>
<p id="msg">Salut !</p>

<script>
  const btn = document.querySelector('#btn')   // sélection
  const msg = document.querySelector('#msg')

  btn.addEventListener('click', () => {        // écoute
    msg.innerText = 'Texte changé 🎉'           // écriture
  })
</script>
