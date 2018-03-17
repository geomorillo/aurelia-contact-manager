# Aurelia Contact Manager Tutorial

This repo contains an implementation of the [Aurelia Framework Contact Manager Tutorial](http://aurelia.io/docs/tutorials/creating-a-contact-manager) this repo differs from the tutorial in that it uses Bootstrap v4 and the tutorial is still using Bootstrap v3.

## App Shell Differences

### Bootstrap v3

```html
<nav class="navbar navbar-default navbar-fixed-top" role="navigation">
  <div class="navbar-header">
    <a class="navbar-brand" href="#">
      <i class="fa fa-user"></i>
      <span>Contacts</span>
    </a>
  </div>
</nav>
```
### Bootstrap v4

```html
<nav class="navbar navbar-light bg-light fixed-top" role="navigation">
  <a class="navbar-brand" href="#">
    <i class="fa fa-user"></i>
    <span>Contacts</span>
  </a>
</nav>
``` 
## Contact List Differences 

### Bootstrap v3

```html
<div class="contact-list">
  <ul class="list-group">
    <li repeat.for="contact of contacts" class="list-group-item ${contact.id === $parent.selectedId ? 'active' : ''}">
      <a route-href="route: contacts; params.bind: {id:contact.id}" click.delegate="$parent.select(contact)">
        <h4 class="list-group-item-heading">${contact.firstName} ${contact.lastName}</h4>
        <p class="list-group-item-text">${contact.email}</p>
      </a>
    </li>
  </ul>
</div>
```
### Bootstrap v4

```html
<div class="contact-list">
  <ul class="list-group">
    <li repeat.for="contact of contacts" class="list-group-item ${contact.id === $parent.selectedId ? 'active' : ''}">
      <a route-href="route: contacts; params.bind: {id:contact.id}" click.delegate="$parent.select(contact)">
        <h4>${contact.firstName} ${contact.lastName}</h4>
        <p>${contact.email}</p>
      </a>
    </li>
  </ul>
</div>
```

## Contact Detail Differences

most of the changes to the styles are in the Contact Details component. Bootstrap v4 removed all of the panel classes
and replaced them with card based classes. Also the form layout classes have been changed.

### Bootstrap v3

```html
<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Profile</h3>
  </div>
  <div class="panel-body">
    <form role="form" class="form-horizontal">
        <div class="form-group">
          <label class="col-sm-2 control-label">First Name</label>
          <div class="col-sm-10">
            <input type="text" placeholder="first name" class="form-control" value.bind="contact.firstName">
          </div>
        </div>
      ...
    </form>
  </div>
</div>
```
### Bootstrap v4

```html
<div class="card">
  <div class="card-header text-white bg-primary">
    <h3>Profile</h3>
  </div>
  <div class="card-body">
      <form role="form">
        <div class="form-group row">
          <label class="col-sm-2 form-label">First Name</label>
          <div class="col-sm-10">
            <input type="text" placeholder="first name" class="form-control" value.bind="contact.firstName">
          </div>
        </div>
        ...
      </form>
  </div>
</div>
```
