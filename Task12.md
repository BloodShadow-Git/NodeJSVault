# Предисловие
В `tailwindcss` последней версии 4.1 (17.01.2026) для создания тёмной темы используется `dark:` + выбранный цвет. [Документация](https://tailwindcss.com/docs/dark-mode)
# Практическое задание №1
`className="border border-gray-200 dark:border-blue-500"`
# Практическое задание №2
Их следует отредактировать для уменьшения разницы между цветом фона и цветами на фото
# Контрольные вопросы
1. Плохая читаемость + большой перепад между цветами
2. Он применяет их автоматически при наличии данных в `localStorage`
3. `localStorage` - это куки сайта и позволяет после выхода восстановить настройки темы сайта
4. Сначала мы выбираем цвет под мобильные устройства и их экраны, а затем остальной зоопарк матриц
5. 
```jsx
   import { useState, useEffect } from 'react';

function ThemeToggle() {
  const [isDark, setIsDark] = useState(false);

  useEffect(() => {
    // Загрузка темы из localStorage или системы
    if (localStorage.theme === 'dark' || 
        (!localStorage.theme && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
      setIsDark(true);
      document.documentElement.classList.add('dark');
    }
  }, []);

  const toggleTheme = () => {
    setIsDark(!isDark);
    document.documentElement.classList.toggle('dark');
    localStorage.theme = isDark ? 'light' : 'dark';
  };

  return (
    <button
      onClick={toggleTheme}
      className="p-3 rounded-full bg-gray-200 dark:bg-gray-800 transition-all duration-300 hover:scale-110 active:scale-95"
    >
      {/* Солнце */}
      <svg 
        className={`w-6 h-6 transition-all duration-500 ${isDark ? 'opacity-0 scale-0' : 'opacity-100 scale-100'}`}
        fill="currentColor" viewBox="0 0 20 20"
      >
        <path d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4 8a4 4 0 11-8 0 4 4 0 018 0zm-.464 4.95l.707.707a1 1 0 001.414-1.414l-.707-.707a1 1 0 00-1.414 1.414zm2.12-10.607a1 1 0 010 1.414l-.706.707a1 1 0 11-1.414-1.414l.707-.707a1 1 0 011.414 0zM17 11a1 1 0 100-2h-1a1 1 0 100 2h1z"/>
      </svg>
      
      {/* Луна */}
      <svg 
        className={`w-6 h-6 absolute transition-all duration-500 ${isDark ? 'opacity-100 scale-100' : 'opacity-0 scale-0'}`}
        fill="currentColor" viewBox="0 0 20 20"
      >
        <path d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"/>
      </svg>
    </button>
  );
}
export default ThemeToggle;
```