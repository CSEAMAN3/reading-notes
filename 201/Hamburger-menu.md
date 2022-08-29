

# Hamburger Menu Example Code

### reference Link
https://alvarotrigo.com/blog/hamburger-menu-css/

Here is the HTML

```
<div class="hamburger-menu">
    <input id="menu__toggle" type="checkbox" />
    <label class="menu__btn" for="menu__toggle">
      <span></span>
    </label>

    <ul class="menu__box">
      <li><a class="menu__item" href="#">Home</a></li>
      <li><a class="menu__item" href="#">About</a></li>
      <li><a class="menu__item" href="#">Team</a></li>
      <li><a class="menu__item" href="#">Contact</a></li>
      <li><a class="menu__item" href="#">Twitter</a></li>
    </ul>
  </div>
```

Here is the css for left menu

```
#menu__toggle {
  opacity: 0;
}
#menu__toggle:checked + .menu__btn > span {
  transform: rotate(45deg);
}
#menu__toggle:checked + .menu__btn > span::before {
  top: 0;
  transform: rotate(0deg);
}
#menu__toggle:checked + .menu__btn > span::after {
  top: 0;
  transform: rotate(90deg);
}
#menu__toggle:checked ~ .menu__box {
  left: 0 !important;
}
.menu__btn {
  position: fixed;
  top: 20px;
  left: 20px;
  width: 26px;
  height: 26px;
  cursor: pointer;
  z-index: 1;
}
.menu__btn > span,
.menu__btn > span::before,
.menu__btn > span::after {
  display: block;
  position: absolute;
  width: 100%;
  height: 2px;
  background-color: #616161;
  transition-duration: .25s;
}
.menu__btn > span::before {
  content: '';
  top: -8px;
}
.menu__btn > span::after {
  content: '';
  top: 8px;
}
.menu__box {
  display: block;
  position: fixed;
  top: 0;
  left: -100%;
  width: 300px;
  height: 100%;
  margin: 0;
  padding: 80px 0;
  list-style: none;
  background-color: #ECEFF1;
  box-shadow: 2px 2px 6px rgba(0, 0, 0, .4);
  transition-duration: .25s;
}
.menu__item {
  display: block;
  padding: 12px 24px;
  color: #333;
  font-family: 'Roboto', sans-serif;
  font-size: 20px;
  font-weight: 600;
  text-decoration: none;
  transition-duration: .25s;
}
.menu__item:hover {
  background-color: #CFD8DC;
}
```

Here is the css for right side menu

```
#menu-toggle {
  opacity: 0;
}
#menu-toggle:checked + .menu-btn > span {
  transform: rotate(45deg);
}
#menu-toggle:checked + .menu-btn > span::before {
  top: 0;
  transform: rotate(0deg);
}
#menu-toggle:checked + .menu-btn > span::after {
  top: 0;
  transform: rotate(90deg);
}
#menu-toggle:checked ~ .menu-box {
  /* this should be left not right */
  right: 0 !important;
}
.menu-btn {
  /* should be fixed */
  position: fixed;
  top: 55px;
  right: 6%;
  width: 30px;
  height: 30px;
  cursor: pointer;
  z-index: 1;
}
.menu-btn > span,
.menu-btn > span::before,
.menu-btn > span::after {
  display: block;
  position: absolute;
  width: 100%;
  height: 3px;
  background-color: var(--eggplant);
  transition-duration: 0.25s;
}
.menu-btn > span::before {
  content: "";
  top: -12px;
}
.menu-btn > span::after {
  content: "";
  top: 12px;
}
.menu-box {
  display: block;
  /* should be fixed */
  position: fixed;
  top: 0;
  /* this should be left not right */
  right: -100%;
  width: 300px;
  height: 100%;
  margin: 0;
  padding: 104px 0;
  list-style: none;
  background-color: #eceff1;
  box-shadow: 2px 2px 6px rgba(0, 0, 0, 0.4);
  transition-duration: 0.25s;
}
.menu-item {
  display: block;
  padding: 12px 24px;
  color: var(--eggplant);
  font-family: "Montserrat", sans-serif;
  font-size: 1.2rem;
  font-weight: 600;
  text-decoration: none;
  transition-duration: 0.25s;
}
.menu-item:hover {
  background-color: var(--grape);
  color: var(--shell);
}
```









