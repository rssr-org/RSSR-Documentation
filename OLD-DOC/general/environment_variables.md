# Environment Variables

An environment variable is a dynamic-named value that can affect the way running processes will behave on a app.
They are part of the environment in which a process runs.
You can find RSSR environment variable in root directory in 4 different file.

---

## .env

This file is RSSR basic environment variables that used in all project running methods.
You can find 3 different variable in this file :

    FILE_VERSION_TYPE='random'

> This variable use for specify versioning type in app

    API_HOST_IN_CLIENT='http://localhost:8000/fake-api'

> ( need question )

    API_HOST_IN_SERVER='http://localhost:8000/fake-api'

> ( need question )

---

## .env.development

This file keep environment variables that use when you start the app in development mode

> PORT=8000

    This is port that app use

> RSSR_REDUX_DEV_TOOLS=true

    With this variable you can control Reduc Dev tools

> RSSR_FETCHER_DEBUG=false

    ( need question )

> RSSR_SKELETON_DEBUG=false

    ( need question )

---

## .env.production

This file keep environment variables that use when you start the app in production mode

    PORT=8000

> This is port that app use

    HOST='0.0.0.0'

> This is address that app should deploy on it after production

    RSSR_REDUX_DEV_TOOLS=false

> With this variable you can control Reduc Dev tools

    RSSR_FETCHER_DEBUG=false

> ( need question )

    RSSR_SKELETON_DEBUG=false

> ( need question )

---

## .env.test

This file keep environment variables that use when you start the app in test mode

    RSSR_REDUX_DEV_TOOLS=false

> With this variable you can control Reduc Dev tools
