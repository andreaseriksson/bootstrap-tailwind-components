# Bootstrap Tailwind components
## Tailwind components for common Bootstrap classes 

## But why?

I really like Tailwind but Bootstrap has been my goto CSS framework for last decades or so. I have also read and talked to people thinking that switching to Tailwind has ha steep(ish) learning curve and the benefits might not be visible in the first hours.

So I made this so you can still get going with some common bootstrap components and have something visible immeditaly. 

However, this is by far not complete and that is not the point. It should just help you to get a smoother transition.

## How to install

Basically you just need to follow the [Tailwind install guide](https://tailwindcss.com/docs/installation) and copy the classes from this repo to your own project.

## JS

You can either pick the normal Bootstrap JS or use the smaller jQuery free [Bootstrap Native library](https://thednp.github.io/bootstrap.native/)

## Examples

### Alert

```html
<div class="alert alert-primary">
  A simple primary alert‚ check it out!
</div>
```

```css
.alert {
  @apply relative px-5 py-3 mb-4 rounded border border-transparent;
}

.alert-primary {
  @apply text-blue-800 bg-blue-200 border-blue-300;
}
```

### Button

```html
<button type="button" class="btn btn-primary">Primary</button>
```

```css
.btn {
  @apply inline-block font-normal text-center px-3 py-2 leading-normal text-base rounded cursor-pointer;
}

.btn-primary {
  @apply text-white bg-blue-600;
}

.btn-primary:hover {
  @apply text-white bg-blue-700
}
```

### Card

```html
<div class="card">
  <img src="https://dummyimage.com/640x4:3/" class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

```css
.card {
  @apply flex flex-col relative bg-white rounded border border-gray-300;
}

.card-body {
  @apply flex-auto p-5;
}

.card-img-top {
  @apply w-full rounded-t;
}

.card-link + .card-link {
  @apply ml-5;
}

.card-text {
  @apply my-0 mb-4;
}

.card-title {
  @apply mb-3 text-xl;
}
```

### Container

The container class in Bootstrap can't be directly ported since Tailwind also have one so do it like:

```html
<main role="main" class="container mx-auto px-6 max-w-5xl">
  <%= render @view_module, @view_template, assigns %>
</main>
```

### Navbar

One thing to notice here is that the reponsive classes in Tailwind can't be extracted to components (AFAIK) and must still be in the markup. 

```html
<nav class="navbar navbar-expand-md navbar-dark fixed-top bg-dark sm:flex-row sm:justify-start">
  <a class="navbar-brand" href="#">Fixed navbar</a>
  <button class="navbar-toggler sm:hidden" type="button" data-toggle="collapse" data-target="#navbarCollapse" aria-controls="navbarCollapse" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse sm:flex sm:w-auto" id="navbarCollapse">
    <ul class="navbar-nav mr-auto sm:flex-row">
      <li class="nav-item active">
        <a class="nav-link sm:px-2" href="#">Home <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link sm:px-2" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link sm:px-2 disabled" href="#">Disabled</a>
      </li>
    </ul>
  </div>
</nav>
```

The CSS for this is a little much but it covers both light and dark mode in both collapsed and non collapsed mode.

```css
.navbar {
  @apply relative flex flex-wrap items-center justify-between py-1 px-4;
}

.fixed-top {
  @apply fixed top-0 right-0 left-0 z-40
}

.navbar-brand {
  @apply inline-block py-1 mr-4 text-xl
}

.navbar-light .navbar-brand {
  @apply text-gray-900
}

.navbar-dark .navbar-brand {
  @apply text-gray-100
}

.navbar-toggler {
  @apply inline-block py-1 px-3 leading-none bg-transparent border border-transparent rounded
}

.navbar-light .navbar-toggler {
  @apply text-gray-500 border-gray-400
}

.navbar-dark .navbar-toggler {
  @apply text-gray-500 border-gray-700
}

.navbar-light .navbar-toggler-icon {
  background-image: url("data:image/svg+xml,<svg viewBox='0 0 30 30' xmlns='http://www.w3.org/2000/svg'><path stroke='rgba(0, 0, 0, 0.5)' stroke-width='2' stroke-linecap='round' stroke-miterlimit='10' d='M4 7h22M4 15h22M4 23h22'/></svg>");
}

.navbar-dark .navbar-toggler-icon {
  background-image: url("data:image/svg+xml,<svg viewBox='0 0 30 30' xmlns='http://www.w3.org/2000/svg'><path stroke='rgba(255, 255, 255, 0.5)' stroke-width='2' stroke-linecap='round' stroke-miterlimit='10' d='M4 7h22M4 15h22M4 23h22'/></svg>");
}

.navbar-toggler-icon {
  content: "";
  @apply inline-block w-6 h-6 align-middle bg-center bg-no-repeat
}

.navbar-collapse {
  @apply hidden w-full flex-grow items-center
}

.navbar-collapse.show, .navbar-collapse.in {
  @apply block
}

.navbar-nav {
  @apply flex flex-col pl-0 mb-0 list-none;
}

.nav-link {
  @apply block py-2 px-4
}

.collapse.show .nav-link, .collapse.in .nav-link {
  @apply px-0
}

.navbar-light .navbar-nav .nav-link  {
  @apply text-gray-600
}

.navbar-light .navbar-nav .nav-link:hover {
  @apply text-gray-800
}

.navbar-light .navbar-nav .active > .nav-link, .navbar-light .navbar-nav .nav-link.active {
  @apply text-gray-900
}

.navbar-light .navbar-nav .nav-link.disabled {
  @apply text-gray-500 pointer-events-none
}

.navbar-dark .navbar-nav .nav-link  {
  @apply text-gray-600
}

.navbar-dark .navbar-nav .nav-link:hover {
  @apply text-gray-500
}

.navbar-dark .navbar-nav .active > .nav-link, .navbar-dark .navbar-nav .nav-link.active {
  @apply text-gray-200
}

.navbar-dark .navbar-nav .nav-link.disabled {
  @apply text-gray-700 pointer-events-none
}
```

### Form

```html
<form>
  <div class="form-group">
    <label for="exampleInputEmail1">Email address</label>
    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Enter email">
    <small id="emailHelp" class="form-text text-muted">We'll never share your email with anyone else.</small>
  </div>
  <div class="form-group">
    <label for="exampleInputPassword1">Password</label>
    <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Password">
  </div>
  <div class="form-group form-check">
    <input type="checkbox" class="form-check-input" id="exampleCheck1">
    <label class="form-check-label" for="exampleCheck1">Check me out</label>
  </div>
  <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

```css
form {
  @apply block;
}

label {
  @apply inline-block mb-2;
}

.form-check {
  @apply relative block pl-5;
}

.form-group {
  @apply mb-4;
}

.form-check-input {
  @apply absolute mt-1 -ml-5;
}

.form-check-label {
  @apply mb-0;
}

.form-control {
  @apply block w-full py-2 px-3 text-base font-normal leading-normal text-gray-700 bg-white border border-gray-400 rounded;
}

.form-inline {
  @apply flex flex-wrap flex-row items-center
}

.form-inline .form-control {
  @apply inline-block w-auto align-middle
}

.form-text {
  @apply block mt-1;
}
```

### Table

```html
<table class="table table-bordered">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">First</th>
      <th scope="col">Last</th>
      <th scope="col">Handle</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
```

```css
th {
  text-align: inherit;
}

.table {
  @apply w-full mb-4 text-gray-900
}

.table thead th {
  @apply align-bottom border-b-2 border-gray-300
}

.table td, .table th {
  @apply p-3 border-t border-gray-300
}

.table.table-bordered {
  @apply border border-gray-300
}

.table-bordered td, .table-bordered th {
  @apply border border-gray-300
}

```

## Screenshots

![Screenshot 2019-11-15 at 21 28 13](https://user-images.githubusercontent.com/897748/68973630-16d72c80-07ef-11ea-8b81-b83fb94437c6.png)

![Screenshot 2019-11-15 at 21 28 28](https://user-images.githubusercontent.com/897748/68973644-1b9be080-07ef-11ea-9208-8be81b194736.png)

![Screenshot 2019-11-15 at 21 28 45](https://user-images.githubusercontent.com/897748/68973656-222a5800-07ef-11ea-9b53-b7936e405f0f.png)

![Screenshot 2019-11-15 at 21 29 01](https://user-images.githubusercontent.com/897748/68973659-26567580-07ef-11ea-9d30-198f3b5ea09c.png)

![Screenshot 2019-11-15 at 21 29 10](https://user-images.githubusercontent.com/897748/68973693-31110a80-07ef-11ea-8e0b-4ce95d18f857.png)

![Screenshot 2019-11-15 at 21 28 39](https://user-images.githubusercontent.com/897748/68973703-35d5be80-07ef-11ea-8bf5-ef7ecafc0ec3.png)

