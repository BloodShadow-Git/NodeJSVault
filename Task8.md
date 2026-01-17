# Практическое задание №1
2. Сразу после root перед закрывающим тегом `</body>`.
# Практическое задание №2
Лучше выделить кнопку "Отмена" для того чтобы пользователь точно понимал что действие можно отменить на этом этапе
# Контрольные вопросы
1. Для того чтобы избежать обрезки модального окна
2. Чтобы элементы вне контейнера не показывались
3. 
```jsx
import { useEffect } from 'react';

const Modal = ({ isOpen, onClose, children }) => {
  if (!isOpen) return null;

	// Здеся
  const handleOverlayClick = (e) => {
    if (e.target === e.currentTarget) {
      onClose();
    }
  };
	// Здеся

  return (
    <div 
      className="modal-overlay" 
      onClick={handleOverlayClick}
    >
      <div className="modal-content">
        {children}
      </div>
    </div>
  );
};
```
4. Интуитивно понятная кнопка закрытия окна/элемента
5. Занимает слишком много места