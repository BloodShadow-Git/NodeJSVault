# Практическое задание №1
```jsx
const { register, handleSubmit, formState: { errors } } = useForm();

<label>Your age</label>
<input type="number" {...register('age',
                {
                    required: 'Возраст обязателен',
                    min: { value: 19, message: 'Возраст должен быть больше 18 лет' },
                    max: { value: 98, message: 'Возраст должен быть младше 99 лет' },
                    valueAsNumber: true
                })}/>
                {errors.age && <p className="text-red-500 text-xs">{errors.age.message}</p>}
```
# Контрольные вопросы
1. `Placeholder` нельзя заменить и локализировать
2. Для привязки к HTML
3. Тем что мы сокращаем количество обновлений логики
4. `errors.{NAME}.message`
5. Использовать `disabled={isSubmitting}`