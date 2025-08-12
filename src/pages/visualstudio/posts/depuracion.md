---
layout: ../../../layouts/BlogLayout.astro
title: Depuración
---

# Depuración

| Atajo        | Descripción                      |
| ------------ | -------------------------------- |
| `F9`         | breakpoint                       |
| `F10`        | paso a paso (sin entrar)         |
| `F11`        | paso a paso (entrando al método) |
| `Shift + F5` | detener                          |

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/visualstudio">Volver</a>
</p>

<style>
  .link-back-container {
    margin: 0;
  }

  .link-back {
    color: var(--color-text);
    text-decoration: none;
    cursor: pointer;
  }

  .link-back:hover {
    color: crimson
  }

pre code {
  background: #232136;
  color: #fff;
  border-radius: 8px;
  padding: 1rem 1.2rem;
  display: block;
  font-size: 1.05rem;
  font-family: 'Fira Mono', 'Consolas', 'Menlo', monospace;
  line-height: 1.6;
  box-shadow: 0 2px 8px rgba(0,0,0,0.04);
  overflow-x: auto;
}

pre {
  background: #232136;
  border-radius: 8px;
  margin: 1.2rem 0;
  padding: 0;
  box-shadow: 0 2px 8px rgba(0,0,0,0.04);
  overflow-x: auto;
}

table {
  width: 100%;
  border-collapse: collapse;
  margin: 1.5rem 0;
  background: var(--color-bg-secondary, #fff);
  font-size: 1rem;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(35,33,54,0.06);
}

th, td {
  border: 1px solid #e1e1e1;
  padding: 0.6rem 1rem;
  text-align: left;
}

th {
  font-weight: 900;
}
</style>
