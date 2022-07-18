# formik.html.io


<!DOCTYPE html>
<html lang="en">
    <script src="https://github.com/faussenouvelles/formik.js.io/blob/main/ella.formik.form.js"></script>
  <head>
    <meta charset="utf-8" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1, shrink-to-fit=no"
    />
    <title>React App</title>
  </head>
  <body>
    <div id="root"></div>
    <!--
      This HTML file is a template.
      If you open it directly in the browser, you will see an empty page.
      You can add webfonts, meta tags, or analytics to this file.
      The build step will place the bundled scripts into the <body> tag.
      To begin the development, run `npm start` or `yarn start`.
      To create a production bundle, use `npm run build` or `yarn build`.
    -->
    <script>
    import React from "react";
// TODO: import useFormik from formik library
import { useFormik } from 'formik';

function App() {
  // TODO: add a const called formik assigned to useFormik()
  const formik = useFormik({
    initialValues: {
      email: "",
      password: "",
    },
    onSubmit: (values) => {
      alert("Login Successful");
    },
    validate: (values) => {
      let errors = {};
      if (!values.email) errors.email = "field required";
      if (!values.password) errors.password = "field required";
      return errors;
    },
  });
  

  return (
    <div>
      //<p>
        The app is ready! You can proceed with the task instructions. TODO:
        build you form here.
      </p>
      <form onSubmit={formik.handleSubmit}>
        <div>Email:</div>
        <input
        id="emailField"
        type="text"
        name="email"
        onChange={formik.handleChange}
        value={formik.values.email}
        />
        {formik.errors.email ? (
          <div id="emailError" style={{ color: red}}>
            {formik.errors.email}
          </div>
        ) : null}
        <div>Password:</div>
        <input 
        id="pswField"
        type="text"
        name="password"
        onChange={formik.handleChange}
        value={formike.value.password}
        />
        <br />
        {formik.errors.password ? (
          <div id="pswError" style={{ color: "red" }}>
            {formik.errors.password}
          </div>
        ) : null}
        <button id="submitBtn" type="submit">
          Submit
        </button>
      </form>
    </div>
  );
}

export default App;

    </script>
  </body>
</html>
