# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

# Contact Form Learning Notes

This project involves creating a **Contact Form** component in React. Below are the key concepts and features learned during this implementation:

## Key Concepts Learned

### 1. **Using Props in Components**
   - **Definition**: Props (short for properties) are used to pass data from a parent component to a child component.
   - **Usage in this Project**:
     - The `Button` component receives props such as `text`, `icon`, `isOutline`, and other attributes using the spread operator (`...rest`).
     - Example:
       ```jsx
       <Button text="VIA SUPPORT CHAT" icon={<MdMessage fontSize="24px" />} />
       ```

### 2. **Form Submission Handling**
   - **Definition**: Forms in React use an `onSubmit` event handler to handle submission logic.
   - **Steps Learned**:
     1. Attach `onSubmit` to the `<form>` element.
     2. Use `event.preventDefault()` to prevent the page from refreshing on form submission.
     3. Use React's `useState` to manage form values dynamically.
     - Example:
       ```jsx
       const onSubmit = (event) => {
           event.preventDefault();
           setName(event.target[0].value);
           setEmail(event.target[1].value);
           setText(event.target[2].value);
           console.log(name, email, text);
       };
       ```

### 3. **Using the `useState` Hook**
   - **Definition**: The `useState` hook allows managing state in functional components.
   - **Usage in this Project**:
     - Used `useState` to initialize and update form fields (`name`, `email`, and `text`).
     - Example:
       ```jsx
       const [name, setName] = useState("himu");
       const [email, setEmail] = useState("code@gmail.com");
       const [text, setText] = useState("hii");
       ```

### 4. **Using the Spread Operator (`...rest`)**
   - **Definition**: The spread operator (`...rest`) allows passing down all remaining props to a child component.
   - **Usage in this Project**:
     - The `Button` component uses `...rest` to accept additional attributes like `onClick` for handling events.
     - Example:
       ```jsx
       const Button = ({ isOutline, icon, text, ...rest }) => {
           return (
               <button {...rest} className={isOutline ? styles.outline_btn : styles.primary_btn}>
                   {icon}
                   {text}
               </button>
           );
       };
       ```
     - This allows passing an `onClick` function to the `Button` component:
       ```jsx
       <Button text="Click Me" onClick={() => alert('Button clicked!')} />
       ```

### 5. **Styling Components with CSS Modules**
   - **Definition**: CSS Modules help in scoping styles locally to the component.
   - **Usage in this Project**:
     - Applied styles from `ContactForm.module.css` and `Button.module.css` to structure and style components.
     - Example:
       ```jsx
       <section className={styles.container}>...</section>
       <button className={isOutline ? styles.outline_btn : styles.primary_btn}>...</button>
       ```

### 6. **Reusable Components**
   - **Definition**: Reusable components promote modular and DRY (Don't Repeat Yourself) principles.
   - **Usage in this Project**:
     - The `Button` component was reused multiple times with different props for chat, call, and email functionalities.
     - Example:
       ```jsx
       <Button isOutline={true} text="VIA EMAIL FORM" icon={<HiMail fontSize="24px" />} />
       ```

### 7. **Dynamic UI Updates**
   - **Definition**: Update the UI dynamically based on the state.
   - **Usage in this Project**:
     - Displayed the updated form values dynamically below the form.
     - Example:
       ```jsx
       <div>{name + " " + email + " " + text}</div>
       ```

## Next Steps to Learn

1. **Advanced State Management**:
   - Use controlled components to bind form inputs to state directly.
   - Explore complex form states with nested objects.

2. **Form Validation**:
   - Add client-side form validation using JavaScript.
   - Explore libraries like `Formik` and `Yup` for advanced validation.

3. **API Integration**:
   - Learn how to submit form data to a backend API using `fetch` or `axios`.

4. **Context API or Redux**:
   - Use `Context API` or `Redux` for managing application-wide states.

5. **Unit Testing**:
   - Write tests for form submission and props using tools like `Jest` and `React Testing Library`.

## Conclusion
This project serves as a foundation for learning key React concepts like props, state management, form handling, reusable components, dynamic UI updates, and using the spread operator. Expanding on this, you can build more complex and interactive forms.
