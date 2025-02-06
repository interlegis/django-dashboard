# django-dashboard
A django app for creating dashboards

Django-dashboard is a Django app for creating dashboards using the Chart.js javascript library.

## Requirements:

- Python > 3.10
- Django > 5.0
- Pandas > 2.2

## Javascript libraries:

- Chart.js > 4.4 (https://www.chartjs.org/docs/latest/)
- JQuery > 3.0 (https://jquery.com/)

## Getting it

You can get django-dashboard using pip:

```
$ pip install django-dashboard
```

## Installing it

To enable `django-dashboard` in your project you need to add `dashboard` to `INSTALLED_APPS` in your project's `settings.py` file:

```python
    INSTALLED_APPS = (
        ...
        'dashboard',
        ...
    )
```

Optionally you can add `dashboard.context_processors.dashboard` to the `context_processors` list inside `OPTIONS` to get a `dashboard` context variable in all templates:

```python
    TEMPLATES = [
        {
            "BACKEND": "django.template.backends.django.DjangoTemplates",
            "DIRS": [BASE_DIR / "templates"],
            "APP_DIRS": True,
            "OPTIONS": {
                "context_processors": [
                    "django.template.context_processors.debug",
                    "django.template.context_processors.request",
                    "django.contrib.auth.context_processors.auth",
                    "django.contrib.messages.context_processors.messages",
                    "dashboard.context_processors.dashboard",
                ],
            },
        },
    ]
```

Add the following to your root urls.py file:

```python
    from dashboard import dashboard
    ...
    urlpatterns = [
        ...
        path("dash/", dashboard.urls),
        ...
    ]
```

Note that the URL path can be whatever you want.