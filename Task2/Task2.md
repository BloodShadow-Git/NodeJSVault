# Предисловие
Tailwindcss был установлен через [официальный сайт (через vite)](https://tailwindcss.com/docs/installation/using-vite)
А в файл `index.css`содержит только строчку `@import "tailwindcss";`.
# Практическое задание №1
App.jsx:
```jsx
function App() {

  return (
    <div>
      <text className="bg-green-500 text-white pt-2 pb-2 pr-6 pl-6 rounded-md">Hello</text>
    </div>
  )
}

export default App
```
Результат в браузере
![[Task2/img1.png]]
# Практическое задание №2
App.jsx:
```jsx
function App() {

  return (
    <div className="flex flex-col items-center pt-5">
        <div className="bg-amber-300 size-5"/>
        <div className="bg-amber-400 size-5"/>
        <div className="bg-amber-500 size-5"/>
        <div className="bg-amber-600 size-5"/>
        <div className="bg-amber-700 size-5"/>
        <div className="bg-amber-800 size-5"/>
        <div className="bg-amber-900 size-5"/>
        <div className="bg-amber-950 size-5"/>
      </div>
  )
}

export default App
```
Результат в браузере
![[img2.png]]
Здесь можно было бы добавить spacing между элементами, но такой задачи нет
# Контрольные вопросы
1. Сначала идут маленькие классы-утилиты, а затем остальное
2. Надо 32 разделить на 4 ($32 / 4 = 8$) и выбрать нужный тип отступа:
	- p - со всех сторон
	- pt - сверху
	- pr - справа
	- pb - снизу
	- pl - слева
3. `tailwind.config.js` в проекте отсутствует :)
4. Использовать псевдоклассы (`hover` и ему подобные)
5. Слева-направо (->)