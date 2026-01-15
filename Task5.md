# Предисловие
Файл `main.jsx` был изменён и имеет следующее содержимое
```jsx
import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import './index.css'
import App from './App.jsx'
import { BrowserRouter, Router } from 'react-router-dom'

createRoot(document.getElementById('root')).render(
  <StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </StrictMode>
)
```
Файл `App.jsx`:
```jsx
import Home from "./pages/Home"
import Notfound from "./pages/notfound"
import { BrowserRouter, Route, Routes } from "react-router-dom"
import Mem from "./pages/Mem"

function App() {
  return (
        <Routes>
          <Route path="Home" element={<Home/>}/>
          <Route path="Mem" element={<Mem/>}/>
          <Route path="*" element={<Notfound/>}/>
        </Routes>
  )
}
export default App
```
`Home.jsx`, `Mem.jsx`, `Notfound.jsx` просто файлы элементов
# Практическое задание №1
`<Route path="checkout" element={<Cart/>}/>`
# Практическое задание №2
Необходимо в `Navbar` изменить `Link` на `NavLink` и добавить `isActive` где требуется
# Контрольные вопросы
1. `<a>` заставляет браузер перезагружать сайт
2. `Path="*"` - ловушка для любых не обработанных ссылок
3. `Клиентский роутеринг` - переход без обновления страницы
4. Его необходимо вынести за пределы `Routes`
5. `NavLink`