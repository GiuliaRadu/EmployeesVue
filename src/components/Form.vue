<template>
  <form id="dataForm">
    <label for="fname">First name:</label><br />
    <input
      type="text"
      id="fname"
      name="fname"
      placeholder="ex:John"
      required
    /><br />

    <label for="lname">Last name:</label><br />
    <input
      type="text"
      id="lname"
      name="lname"
      placeholder="ex:Doe"
      required
    /><br />

    <label for="email">Email:</label><br />
    <input
      type="text"
      id="email"
      name="email"
      placeholder="ex:john@doe.com"
      required
    /><br /><br />

    <label for="sex">Sex:</label>
    <select name="sex" id="sex" required>
      <option value="" selected disabled hidden>Choose here</option>
      <option value="male">Male</option>
      <option value="female">Female</option>
      <option value="other">Other</option>
    </select>

    <label for="dateOfBirth">Date of birth:</label>

    <input
      type="date"
      id="dateOfBirth"
      name="birthdate"
      value="2002-04-23"
      min="1990-01-01"
      max="2003-01-01"
      required
    />
    <br />
    <label for="img">Select image:</label>

    <input type="file" id="img" name="img" accept="image/*" required />
    <br />
    <br />

    <input type="submit" value="Submit" id="submit" />
  </form>
</template>

<script>
export default {
  name: "Form",
};
</script>

<style scoped>
</style>