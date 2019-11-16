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

###Alert

```html
<div class="alert alert-primary">
  A simple primary alert‚Äîcheck it out!
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

###Button

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

###Card

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




## Screenshots

![Screenshot 2019-11-15 at 21 28 13](https://user-images.githubusercontent.com/897748/68973630-16d72c80-07ef-11ea-8b81-b83fb94437c6.png)

![Screenshot 2019-11-15 at 21 28 28](https://user-images.githubusercontent.com/897748/68973644-1b9be080-07ef-11ea-9208-8be81b194736.png)

![Screenshot 2019-11-15 at 21 28 45](https://user-images.githubusercontent.com/897748/68973656-222a5800-07ef-11ea-9b53-b7936e405f0f.png)

![Screenshot 2019-11-15 at 21 29 01](https://user-images.githubusercontent.com/897748/68973659-26567580-07ef-11ea-9d30-198f3b5ea09c.png)

![Screenshot 2019-11-15 at 21 29 10](https://user-images.githubusercontent.com/897748/68973693-31110a80-07ef-11ea-8e0b-4ce95d18f857.png)

![Screenshot 2019-11-15 at 21 28 39](https://user-images.githubusercontent.com/897748/68973703-35d5be80-07ef-11ea-8bf5-ef7ecafc0ec3.png)

