# edu_uh_cas
This is the University of Hawaii CAS authentication example based on [django-cas-ng](https://github.com/mingchen/django-cas-ng).


## Getting started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites
This is a django authentication backend for University of Hawaii CAS authentication. All settings are same as the [django-cas-ng](https://github.com/mingchen/django-cas-ng).

### Installation
Install the [django-cas-ng](https://github.com/mingchen/django-cas-ng) and set its settings. Copy this backend as an app on your django project. Config your own attributes on the 'configure_user()'.
Change your settings,
```python
AUTHENTICATION_BACKENDS = [
    'django.contrib.auth.backends.ModelBackend',

    #'django_cas_ng.backends.CASBackend',
    'edu_uh_cas.backends.UHCASBackend',
]
```
### Notes
[University of Hawaii uses a CAS system](https://www.hawaii.edu/bwiki/pages/viewpage.action?pageId=230230565) is based on LDAP system. Django user models' atttibutes are different with LDAP's names of attribute, so the [django-cas-ng](https://github.com/mingchen/django-cas-ng) cannot save extra information of LDAP based CAS information. The [django-cas-ng](https://github.com/mingchen/django-cas-ng) has good django authentication backends but unfortunately it does not pass 'attributes' to 'configure_user()' for configuration of users data of local user models. I put one word 'attribute' and add extras for users information. Most codes are same except that.
