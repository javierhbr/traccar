# Documentation

### base - https://docs.minimals.cc





### colors - https://docs.minimals.cc/colors

# Colors

[Latest](</colors>)[v6.1.0](</v6/colors>)[v5](</v5/colors>)

Custom global color inside:

  * `src/theme/theme-config.ts`
  * `src/theme/core/palette.ts`

* * *

#### Color tools

###### Material color

<https://mui.com/customization/color/>.

  

###### Eva color

<https://colors.eva.design/>.

We recommend picking colors with these values for **Eva tool** :

  * Lighter : `100`
  * Light : `300`
  * Main : `500`
  * Dark : `700`
  * Darker : `900`

    
    
    {
      "primary": {
        "lighter": "#C8FAD6",
        "light": "#5BE49B",
        "main": "#00A76F",
        "dark": "#007867",
        "darker": "#004B50",
        "contrastText": "#FFFFFF"
      },
    ...
    }

src/theme/theme-config.ts

* * *

###### Reference:

  * <https://minimals.cc/components/foundation/colors>



### typography - https://docs.minimals.cc/typography

# Typography

[Latest](</typography>)[v6.1.0](</v6/typography>)[v5](</v5/typography>)

Custom global typography inside:

  * `src/theme/theme-config.ts`
  * `src/theme/core/typography.ts`

* * *

**Install new font**

    
    
     npm install @fontsource-variable/inter

**Update**

  * `src/global.css`
  * `src/theme/theme-config.ts`

src/global.css

    
    
    @import '@fontsource-variable/inter';

  
src/theme/theme-config.ts

    
    
    fontFamily: {
      primary: 'Inter Variable',
      ...
    },

* * *

###### Reference:

  * <https://fontsource.org/fonts/inter>
  * <https://minimals.cc/components/foundation/typography>



### icons - https://docs.minimals.cc/icons

# Icons

* * *

##### Material Icon

<https://mui.com/components/material-icons/>

    
    
    import AdbIcon from '@mui/icons-material/Adb';
    import AddIcon from '@mui/icons-material/Add';
    import AppleIcon from '@mui/icons-material/Apple';
    import AccountCircleIcon from '@mui/icons-material/AccountCircle';
    import AirplanemodeActiveIcon from '@mui/icons-material/AirplanemodeActive';
     
    function App() {
      return (
        <>
          <AdbIcon color="action" />
          <AddIcon color="disabled" />
          <AccountCircleIcon color="error" />
          <AirplanemodeActiveIcon color="inherit" />
          <AppleIcon color="primary" />
          <AppleIcon color="secondary" />
        </>
      );
    }

* * *

##### Iconify Icon

<https://iconify.design/icon-sets>

    
    
    import Iconify from 'src/components/Iconify';
     
    function App() {
      return (
        <>
          <Iconify icon="eva:clock-fill" sx={{ color: 'primary.main' }} />
          <Iconify icon="eva:charging-fill" sx={{ color: 'secondary.main' }} />
          <Iconify icon="eva:alert-circle-fill" sx={{ color: 'info.main' }} />
          <Iconify icon="eva:color-palette-fill" sx={{ color: 'warning.main' }} />
          <Iconify icon="eva/arrow-circle-down-fill" sx={{ color: 'error.main' }} />
        </>
      );
    }

* * *

##### Local Icon

    
    
    import SvgColor from 'src/components/svg-color';
     
    function App() {
      return (
        <>
          <SvgColor src="/assets/icons/browser-edge.svg" sx={{ color: 'primary.main' }} />
          <SvgColor src="/assets/icons/browser-edge.svg" sx={{ color: 'secondary.main' }} />
          <SvgColor src="/assets/icons/elephant.svg" sx={{ color: 'info.main' }} />
          <SvgColor src="/assets/icons/json-logo.svg" sx={{ color: 'success.main' }} />
          <SvgColor src="/assets/icons/love-camera.svg" sx={{ color: 'warning.main' }} />
          <SvgColor src="/assets/icons/shield.svg" sx={{ color: 'error.main' }} />
        </>
      );
    }

* * *

###### Reference:

  * <https://minimals.cc/components/foundation/icons>



### shadows - https://docs.minimals.cc/shadows

# Shadows

[Latest](</shadows>)[v5](</v5/shadows>)

  * Custom `shadows` inside `src/theme/core/shadows`
  * Custom `customShadows` inside `src/theme/core/customShadows`

* * *

###### Reference:

  * <https://minimals.cc/components/foundation/shadows>



### css-vars - https://docs.minimals.cc/css-vars

# Css vars

Feature available in v6.

* * *

**Color**

<https://mui.com/material-ui/experimental-api/css-theme-
variables/usage/#using-theme-variables>

    
    
    // Old
    color: theme.palette.common.white,
     
    // New
    color: theme.vars.palette.common.white,

**Alpha**

    
    
     // Old
    import { alpha } from '@mui/material/styles';
    alpha(theme.palette.text.primary, 0.2)
     
    // New
    import { varAlpha } from 'minimal-shared/utils';
    varAlpha(theme.vars.palette.text.primaryChannel, 0.2)

**Dark mode**

  * <https://mui.com/material-ui/experimental-api/css-theme-variables/overview/#styling>

  * <https://mui.com/material-ui/experimental-api/css-theme-variables/migration/#4-refactor-custom-styles-to-use-the-attribute-selector>

Old

    
    
    import { alpha } from '@mui/material/styles';
     
    <Box
      sx={{
        color: theme.palette.mode === 'light' ? 'primary.main' : 'primary.light',
        boxShadow: `-80px 80px 80px ${
        theme.palette.mode === 'light'
        ? alpha(theme.palette.grey[500], 0.48)
        : alpha(theme.palette.common.black, 0.24)
        }`,
      }}
    >
    Box
    </Box>

  
New

    
    
    import { varAlpha } from 'minimal-shared/utils';
     
    <Box
      sx={{
        color: 'primary.main',
        boxShadow: `-80px 80px 80px ${varAlpha(theme.vars.palette.grey['500Channel'], 0.48)}`,
        ...theme.applyStyles('dark', {
        color: 'primary.light',
        boxShadow: `-80px 80px 80px ${varAlpha(theme.vars.palette.common.blackChannel, 0.24)}`,
        }),
      }}
    >
    Box
    </Box>



### logo - https://docs.minimals.cc/logo

# Logo

[Latest](</logo>)[v5](</v5/logo>)

  * Change logo in `src/components/logo`.
  * Change favicon in `public/favicon.ico`.

* * *

##### Change favicon

  * Upload logo in <https://favicon.io/favicon-converter/>.
  * Download the resource and unzip.
  * Copy and overwrite to folder `public/favicon.ico`.

Next.jsVite.js

    
    
    // src/app/layout.(jsx | tsx)
     
    export const metadata: Metadata = {
      icons: [
        { rel: 'icon', url: '/favicon.ico', },
      ],
    };

##### Change logo (image)

Use from `public` folder

    
    
    const logo = (
      <Box alt="logo" component="img" src={`/logo/logo-single.svg`} width={width} height={height} />
    );

src/components/logo/logo

##### Change logo (svg)

Use with svg

    
    
    const logo = (
      <svg xmlns="http://www.w3.org/2000/svg" width="100%" height="100%" viewBox="0 0 512 512">
        <defs>
          <linearGradient id={`${gradientId}-1`} x1="100%" x2="50%" y1="9.946%" y2="50%">
            <stop offset="0%" stopColor={PRIMARY_DARK} />
            <stop offset="100%" stopColor={PRIMARY_MAIN} />
          </linearGradient>
     
          <linearGradient id={`${gradientId}-2`} x1="50%" x2="50%" y1="0%" y2="100%">
            <stop offset="0%" stopColor={PRIMARY_LIGHT} />
            <stop offset="100%" stopColor={PRIMARY_MAIN} />
          </linearGradient>
     
          <linearGradient id={`${gradientId}-3`} x1="50%" x2="50%" y1="0%" y2="100%">
            <stop offset="0%" stopColor={PRIMARY_LIGHT} />
            <stop offset="100%" stopColor={PRIMARY_MAIN} />
          </linearGradient>
        </defs>
     
        <g fill={PRIMARY_MAIN} fillRule="evenodd" stroke="none" strokeWidth="1">
          <path
            fill={`url(#${`${gradientId}-1`})`}
            d="M183.168 285.573l-2.918 5.298-2.973 5.363-2.846 5.095-2.274 4.043-2.186 3.857-2.506 4.383-1.6 2.774-2.294 3.939-1.099 1.869-1.416 2.388-1.025 1.713-1.317 2.18-.95 1.558-1.514 2.447-.866 1.38-.833 1.312-.802 1.246-.77 1.18-.739 1.111-.935 1.38-.664.956-.425.6-.41.572-.59.8-.376.497-.537.69-.171.214c-10.76 13.37-22.496 23.493-36.93 29.334-30.346 14.262-68.07 14.929-97.202-2.704l72.347-124.682 2.8-1.72c49.257-29.326 73.08 1.117 94.02 40.927z"
          />
          <path
            fill={`url(#${`${gradientId}-2`})`}
            d="M444.31 229.726c-46.27-80.956-94.1-157.228-149.043-45.344-7.516 14.384-12.995 42.337-25.267 42.337v-.142c-12.272 0-17.75-27.953-25.265-42.337C189.79 72.356 141.96 148.628 95.69 229.584c-3.483 6.106-6.828 11.932-9.69 16.996 106.038-67.127 97.11 135.667 184 137.278V384c86.891-1.611 77.962-204.405 184-137.28-2.86-5.062-6.206-10.888-9.69-16.994"
          />
          <path
            fill={`url(#${`${gradientId}-3`})`}
            d="M450 384c26.509 0 48-21.491 48-48s-21.491-48-48-48-48 21.491-48 48 21.491 48 48 48"
          />
        </g>
      </svg>
    );

src/components/logo/logo

##### Usage

    
    
    import Logo from 'src/components/logo';
     
    <Logo sx={{ width: 64, height: 64 }} />



### layout - https://docs.minimals.cc/layout

# Layout

[Latest](</layout>)[v5](</v5/layout>)

* * *

##### Change size

  * in `src/layouts/core/layout-section.tsx`

    
    
    <GlobalStyles
      styles={{
        body: {
          '--layout-nav-zIndex': 1101,
          '--layout-nav-mobile-width': '320px',
          '--layout-header-blur': '8px',
          '--layout-header-zIndex': 1100,
          '--layout-header-mobile-height': '64px',
          '--layout-header-desktop-height': '72px',
          ...cssVars,
        },
      }}
    />

src/layouts/core/layout-section.tsx

* * *

##### Change Menu, Navigation

Find `nav-config.(ts | js)` files to adjust items.

Example:

  * `<MainLayout/>` : src/layouts/config-nav-main
  * `<DashboardLayout>` : src/layouts/config-nav-dashboard

* * *

##### Reference

  * <https://minimals.cc/components/extra/layout/>



### navigation - https://docs.minimals.cc/navigation

# Navigation

Instructions to change the default menu to multiple menus.

* * *

[Watch video](<https://youtu.be/oaxsjQDbguY>)

* * *

**Results:**

![minimal-preview](/assets/images/change-nav/navigation-desktop.jpg)![minimal-
preview](/assets/images/change-nav/navigation-mobile.jpg)



### settings - https://docs.minimals.cc/settings

# Settings

[Latest](</settings>)[v6.1.0](</v6/settings>)[v5](</v5/settings>)

This section will describe how you settings your theme.

* * *

##### Change default settings

Remove `local storage` or `cookies storage` when you change settings.

With local storage

    
    
    // src/App.(jsx | tsx) or src/app/layout.(jsx | tsx)
     
    import { defaultSettings } from 'src/components/settings';
     
    <SettingsProvider defaultSettings={defaultSettings}>
      ...
    </SettingsProvider>

  
With cookies storage (Next.js only)

    
    
    // src/App.(jsx | tsx) or src/app/layout.(jsx | tsx)
     
    import { defaultSettings } from 'src/components/settings';
    import { detectSettings } from 'src/components/settings/server';
     
    export default async function RootLayout({ children }: RootLayoutProps) {
      const cookieSettings = await detectSettings();
     
      return (
        <html lang="en" dir={cookieSettings.dir} suppressHydrationWarning>
          <body>
            <SettingsProvider cookieSettings={cookieSettings} defaultSettings={defaultSettings}>
              ...
            </SettingsProvider>
          </body>
        </html>
      );
    }
     

* * *

##### Base theme

Without settings and locales.

    
    
    // src/theme/create-theme.(js | ts)
     
    export const baseTheme = {
      colorSchemes: {
        light: {
          palette: palette.light,
          shadows: shadows.light,
          customShadows: customShadows.light
        },
        dark: {
          palette: palette.dark,
          shadows: shadows.dark,
          customShadows: customShadows.dark
        }
      },
      mixins,
      components,
      typography,
      shape: { borderRadius: 8 },
      direction: themeConfig.direction,
      cssVariables: themeConfig.cssVariables,
      defaultColorScheme: themeConfig.defaultMode
    }
     
    export function createTheme({ themeOverrides }) {
      const theme = createMuiTheme(baseTheme, themeOverrides);
     
      return theme;
    }

* * *

##### With localization

MUI localization components

  * <https://mui.com/material-ui/guides/localization/>.

    
    
    // src/theme/create-theme.(js | ts)
     
    export const baseTheme = {
      colorSchemes: {
        light: {
          palette: palette.light,
          shadows: shadows.light,
          customShadows: customShadows.light
        },
        dark: {
          palette: palette.dark,
          shadows: shadows.dark,
          customShadows: customShadows.dark
        }
      },
      mixins,
      components,
      typography,
      shape: { borderRadius: 8 },
      direction: themeConfig.direction,
      cssVariables: themeConfig.cssVariables,
      defaultColorScheme: themeConfig.defaultMode
    }
     
    export function createTheme({ themeOverrides, localeComponents }) {
      const theme = createMuiTheme(baseTheme, localeComponents, themeOverrides);
     
      return theme;
    }

* * *

##### With settings

    
    
    // src/theme/create-theme.(js | ts)
     
    export const baseTheme = {
      colorSchemes: {
        light: {
          palette: palette.light,
          shadows: shadows.light,
          customShadows: customShadows.light
        },
        dark: {
          palette: palette.dark,
          shadows: shadows.dark,
          customShadows: customShadows.dark
        }
      },
      mixins,
      components,
      typography,
      shape: { borderRadius: 8 },
      direction: themeConfig.direction,
      cssVariables: themeConfig.cssVariables,
      defaultColorScheme: themeConfig.defaultMode
    }
     
    export function createTheme({ settingsState, themeOverrides }) {
      const updatedCore = settingsState ? updateCoreWithSettings(baseTheme, settingsState) : baseTheme;
     
      const updatedComponents = settingsState
        ? updateComponentsWithSettings(components, settingsState)
        : {};
     
      const theme = createMuiTheme(updatedCore, updatedComponents, themeOverrides);
     
      return theme;
    }

* * *

###### Related files:

  * `src/App.js` or `src/app/layout.js`
  * `src/components/settings`



### styles - https://docs.minimals.cc/styles

### Page Not Found!

### How to fix?

Try clearing **your browser cache** / opening in a **different browser** or
check link.



### config - https://docs.minimals.cc/config

### Page Not Found!

### How to fix?

Try clearing **your browser cache** / opening in a **different browser** or
check link.



### mui-overrides - https://docs.minimals.cc/mui-overrides

# Global overrides MUI components

Overrides the components of the MUI in the directory
`src/theme/core/components`.

* * *

**styleOverrides**

<https://mui.com/material-ui/customization/theme-components/#theme-style-
overrides>

* * *

**defaultProps**

<https://mui.com/material-ui/customization/theme-components/#theme-default-
props>

* * *

**Example:**

    
    
     // src/theme/core/components/appbar.tsx
     
    const MuiAppBar: Components<Theme>['MuiAppBar'] = {
      defaultProps: { color: 'transparent' },
      styleOverrides: { root: { boxShadow: 'none' } },
    };

* * *

**Reference:**

  * <https://mui.com/components/>
  * <https://mui.com/material-ui/customization/theme-components/>
  * <https://mui.com/customization/theme-components/#global-style-overrides>

    
    
    src
      ├── theme/core/components
        ├── accordion.jsx
        ├── alert.jsx
        ├── appbar.jsx
        ├── ...
    ...

######

Before Overrides (MUI theme)

![Before overrides](/assets/images/button/mui.webp)

######

After Overrides (Minimal theme)

![After overrides](/assets/images/button/minimal.webp)

* * *

> The change will apply globally for MUI component.

> This helps you to deeply customize your style, to suit your design.



### routing - https://docs.minimals.cc/routing

# Routing

This article does not cover the settings in `next.js` because the `next.js`
documentation is quite complete [here](<https://nextjs.org/docs/app/building-
your-application/routing>)

* * *

##### Create react app, Vite.js

The routing is based on [react-
router](<https://reactrouter.com/start/framework/installation>).

In this page you will find how to add new routes and how we handle existing
routes.

You can find the template's router configuration in
`src/routes/sections/index.js` contains all routes of our template.

* * *

##### Add a new item navigation

  * Apply version `CRA`, `Vite.js`, `Next.js`.
  * Example: Add a new item navigation in the dashboard layout.

Example base on starter version

    
    
    // src/layouts/nav-config-dashboard.tsx
     
    export const navData = [
      {
        subheader: 'Overview',
        items: [
          {
            title: 'One',
            path: paths.dashboard.root,
            icon: ICONS.dashboard,
            info: <Label>v{CONFIG.appVersion}</Label>,
          },
          { title: 'Two', path: paths.dashboard.two, icon: ICONS.ecommerce },
          { title: 'Three', path: paths.dashboard.three, icon: ICONS.analytics },
          { title: 'New page', path: '/dashboard/new-page', icon: ICONS.analytics },
        ],
      },
      {
        subheader: 'Management',
        items: [
          {
            title: 'Group',
            path: paths.dashboard.group.root,
            icon: ICONS.user,
            children: [
              { title: 'Four', path: paths.dashboard.group.root },
              { title: 'Five', path: paths.dashboard.group.five },
              { title: 'Six', path: paths.dashboard.group.six },
            ],
          },
        ],
      },
    ];
     

##### Add a new route (Vite.js)

Example base on starter version

    
    
    // src/routes/sections/dashboard.tsx
     
    const IndexPage = lazy(() => import('src/pages/dashboard/one'));
    const PageTwo = lazy(() => import('src/pages/dashboard/two'));
    const PageThree = lazy(() => import('src/pages/dashboard/three'));
    const PageFour = lazy(() => import('src/pages/dashboard/four'));
    const PageFive = lazy(() => import('src/pages/dashboard/five'));
    const PageSix = lazy(() => import('src/pages/dashboard/six'));
    const NewPage = lazy(() => import('src/pages/dashboard/new-page'));
     
    const dashboardLayout = () => (
      <DashboardLayout>
        <Suspense fallback={<LoadingScreen />}>
          <Outlet />
        </Suspense>
      </DashboardLayout>
    );
     
    export const dashboardRoutes = [
      {
        path: 'dashboard',
        element: CONFIG.auth.skip ? dashboardLayout() : <AuthGuard>{dashboardLayout()}</AuthGuard>,
        children: [
          { element: <IndexPage />, index: true },
          { path: 'two', element: <PageTwo /> },
          { path: 'three', element: <PageThree /> },
          { path: 'new page', element: <NewPage /> },
          {
            path: 'group',
            children: [
              { element: <PageFour />, index: true },
              { path: 'five', element: <PageFive /> },
              { path: 'six', element: <PageSix /> },
            ],
          },
        ],
      },
    ];

##### Add a new route (Next.js)

  * create `src/app/dashboard/new-page/page.(jsx | tsx)`
  * <https://nextjs.org/docs/app/building-your-application/routing/pages>

* * *

##### Set the index page

Set default page when visit website.

_Check out the full and starter versions to see the difference_

    
    
     export const routesSection = [
     
        { // Set index page with skip home page
          path: '/',
          element: <Navigate to={CONFIG.auth.redirectPath} replace />,
        },
        { // Set index page with home page
          path: '/',
          element: (
            <MainLayout>
              <Outlet />
            </MainLayout>
          ),
          children: [{ element: <HomePage />, index: true }],
        },
    ];

src/routes/sections/index.js

* * *

##### Usage

    
    
    import Link from '@mui/material/Link';
    import { RouterLink } from 'src/routes/components';
     
    <Link component={RouterLink} href="/new" underline="none" variant="subtitle2">
      Go to About us
    </Link>;

* * *

##### Display with role

<https://minimals.cc/components/extra/navigation-bar>

<https://minimals.cc/dashboard/permission>

    
    
    const navData = [
      {
        subheader: 'Marketing',
        items: [
          {
            title: 'Landing',
            path: '/landing',
            icon: <Iconify icon="carbon:bat" width={1} />,
            roles: ['admin'],
            caption: 'Display only admin role',
          },
          {
            title: 'Services',
            path: '/services',
            icon: <Iconify icon="carbon:cyclist" width={1} />,
            roles: ['admin', 'user'],
          },
        ],
      },
    ];

config-navigation.js



### subfolder - https://docs.minimals.cc/subfolder

# Subfolder

Applicable from **v6.1.0** and above.

* * *

##### Vite.js

.env

    
    
    VITE_ASSETS_DIR=/sub

  
vite.config.ts

    
    
    export default defineConfig({
      base: '/sub/',
      ...
    });

  
src/main.tsx

    
    
    <BrowserRouter basename="sub">
      ...
    </BrowserRouter>

* * *

##### Next.js

.env

    
    
    NEXT_PUBLIC_ASSETS_DIR=/sub

  
next.config.mjs

    
    
    const nextConfig = {
      basePath: '/sub',
      ...
    };



### authentication/jwt - https://docs.minimals.cc/authentication/jwt

# JWT

[**For version v5**](</v5/jwt/>)

* * *

**Choose an authentication strategy.**

Update `src/config-global.ts`

    
    
    auth: {
      method: 'jwt',
    },

**Update`.env`**

    
    
    VITE_SERVER_URL=https://api-dev-minimal-v6.vercel.app

.env



### authentication/firebase - https://docs.minimals.cc/authentication/firebase

# Firebase

[**For version v5**](</v5/firebase/>).

[Demo flow](<https://youtu.be/4kHKaWaLUSw>)

* * *

**Choose an authentication strategy.**

Update `src/config-global.ts`

    
    
    auth: {
      method: 'firebase',
    },

**Create Firestore Database**

[ Watch video](<https://youtu.be/ouGhTuIy3hs>)

Update rule in Cloud Firestore

    
    
    service cloud.firestore {
        match /databases/{database}/documents {
        match /{document=**} {
        allow read, write: if request.auth.uid != null;
        }
      }
    }

**Get API key**

    
    
     VITE_FIREBASE_API_KEY=
    VITE_FIREBASE_AUTH_DOMAIN=
    VITE_FIREBASE_PROJECT_ID=
    VITE_FIREBASE_STORAGE_BUCKET=
    VITE_FIREBASE_MESSAGING_SENDER_ID=
    VITE_FIREBASE_APPID=

.env

![minimal-preview](/assets/images/auth/firebase-config.jpg)



### authentication/amplify - https://docs.minimals.cc/authentication/amplify

# Amplify

[**For version v5**](</v5/amplify/>).

[Demo flow](<https://youtu.be/aZXhjPbnbqw>)

* * *

**Choose an authentication strategy.**

Update `src/config-global.ts`

    
    
    auth: {
      method: 'amplify',
    },

**Get API key**

[ Watch video](<https://www.youtube.com/watch?v=-qo5GFdN-Ck>)  
  

    
    
    VITE_AWS_AMPLIFY_USER_POOL_ID=

.env

![minimal-preview](/assets/images/auth/amplify-user-pool-id.jpg)

    
    
    VITE_AWS_AMPLIFY_USER_POOL_WEB_CLIENT_ID=

.env

![minimal-preview](/assets/images/auth/amplify-user-pool-web-client-id.jpg)



### authentication/auth0 - https://docs.minimals.cc/authentication/auth0

# Auth0

[**For version v5**](</v5/auth0/>).

[Demo flow](<https://youtu.be/PWoGb5r5xgQ>)

* * *

**Choose an authentication strategy.**

Update `src/config-global.ts`

    
    
    auth: {
      method: 'auth0',
    },

**Get API key** ([view](<https://auth0.com/blog/complete-guide-to-react-user-
authentication/>))

    
    
    VITE_AUTH0_DOMAIN=

.env

![minimal-preview](/assets/images/auth/auth0-domain.jpg)

    
    
    VITE_AUTH0_CLIENT_ID=

.env

![minimal-preview](/assets/images/auth/auth0-client-id.jpg)

    
    
    VITE_AUTH0_CALLBACK_URL=

.env

![minimal-preview](/assets/images/auth/auth0-callback.jpg)



### authentication/user-info - https://docs.minimals.cc/authentication/user-info

# Get User Info

* * *

Change

    
    
    const { user } = useMockedUser();

  
To

    
    
    import { useAuthContext } from 'src/auth/hooks';
    const { user } = useAuthContext();



### environment-variables - https://docs.minimals.cc/environment-variables

# Environment variables

* * *

##### Create react app

<https://create-react-app.dev/docs/adding-custom-environment-variables/>

Use a prefix `REACT_APP_`

    
    
    REACT_APP_MAP=
    REACT_APP_WEBSITE_URL=

.env  
Usage

    
    
    process.env.REACT_APP_MAP;
    process.env.REACT_APP_WEBSITE_URL;

* * *

##### Next.js

<https://nextjs.org/docs/api-reference/next.config.js/environment-variables>

Use a prefix `NEXT_PUBLIC_`

    
    
    NEXT_PUBLIC_MAP=
    NEXT_PUBLIC_WEBSITE_URL=

.env  
Usage

    
    
    process.env.NEXT_PUBLIC_MAP;
    process.env.NEXT_PUBLIC_WEBSITE_URL;

* * *

##### Vite.js

<https://vitejs.dev/guide/env-and-mode.html>

Use a prefix `VITE_`

    
    
    VITE_MAP=
    VITE_WEBSITE_URL=

.env  
Usage

    
    
    import.meta.env.VITE_MAP;
    import.meta.env.VITE_WEBSITE_URL;



### api-calls - https://docs.minimals.cc/api-calls

# API Calls

* * *

##### Basic example

    
    
    import useSWR from 'swr';
    import { fetcher } from 'src/utils/axios';
     
    function ProductList() {
      const { data, error, isLoading } = useSWR('/api/product/list', fetcher);
     
      if (error) return <div>failed to load</div>;
     
      if (isLoading) return <div>loading...</div>;
     
      return (
        <>
          {data.products.map((product) => (
            <div key={product.id}>{product.name}</div>
          ))}
        </>
      );
    }

* * *

##### Set BaseURL

    
    
    REACT_APP_HOST_API=https://www.your-domain.com

.env  

    
    
    const axiosInstance = axios.create({ baseURL: process.env.REACT_APP_HOST_API });

src/utils/axios.js  

    
    
    import useSWR from 'swr';
    import axios, { fetcher } from 'src/utils/axios';
     
    const fetcher = (url) => axios.get(url).then((res) => res.data);
     
    function ProductList() {
      // const { data, error, isLoading } = useSWR(`https://www.your-domain.com/api/product/list`, fetcher);
      const { data, error, isLoading } = useSWR(`/api/product/list`, fetcher);
     
      if (error) return <div>failed to load</div>;
     
      if (isLoading) return <div>loading...</div>;
     
      return (
        <>
          {data.products.map((product) => (
            <div key={product.id}>{product.name}</div>
          ))}
        </>
      );
    }

* * *

##### Without BaseURL

We provide a demo API with a base URL. To avoid conflicts during development,
you can work with parallel API calls without the base URL. You can replace it
after development is complete.

    
    
    import useSWR from 'swr';
    import axios from 'axios';
     
    const fetcher = (url) => axios.get(url).then((res) => res.data);
     
    function ProductList() {
      const { data, error, isLoading } = useSWR(
        `https://www.your-domain.com/api/product/list`,
        fetcher
      );
     
      if (error) return <div>failed to load</div>;
     
      if (isLoading) return <div>loading...</div>;
     
      return (
        <>
          {data.products.map((product) => (
            <div key={product.id}>{product.name}</div>
          ))}
        </>
      );
    }



### multi-language - https://docs.minimals.cc/multi-language

# Multi Language

* * *

##### Setup / Remove

Search with keyword `src/locales` then setup the relevant components.

![multi-language](/assets/images/multi-language.jpg)

* * *

##### Add new content

    
    
    {
      "heading": "Lorem Ipsum is simply dummy text of the printing and typesetting industry",
      "nested": {
        "nested1": "nested En"
      }
    }

src/locales/en.json  

    
    
    {
      "heading": "Le Lorem Ipsum est simplement du faux texte employé dans la composition et la mise en page avant impression",
      "nested": {
        "nested1": "nested Fr"
      }
    }

src/locales/fr.json

* * *

##### Usage

    
    
    import { useLocales, useTranslate } from 'src/locales';
     
    function MultiLanguage() {
      const { t, onChangeLang } = useTranslate();
     
      const { allLang, currentLang } = useLocales();
     
      return (
        <>
          <RadioGroup row value={currentLang.value} onChange={(event) => onChangeLang(event.target.value)}>
            {allLang.map((lang) => (
              <FormControlLabel key={lang.label} value={lang.value} label={lang.label} control={<Radio />} />
            ))}
          </RadioGroup>
     
          <Typography variant="h2">{t('heading')}</Typography>
          <Typography variant="body2">{t('nested.nested1')}</Typography>
        </>
      );
    }

* * *

###### Reference:

  * <https://minimals.cc/components/extra/multi-language>
  * <https://react.i18next.com/>
  * <https://mui.com/material-ui/guides/localization/#main-content>



### structure - https://docs.minimals.cc/structure

# Structure

* * *
    
    
    root
      ├── public
      ├── src
          ├── types
          ├── assets
          ├── components
          ├── pages OR app
          ├── hooks
          ├── layouts
          ├── sections
          ├── theme
          ├── utils
          ├── routes
          ├── ...
      ├── next.config.js
      ├── package.json
      ├── ...

![structure](/assets/images/structure.jpg)

* * *

##### Remove & Clean

Depending on the needs of each project, there will be components that are not
needed.

Below is the order of precedence for deleting components:

**Step 1:**

Delete unused pages in `/pages`or `/app`.

Example: delete `src/pages/contact-us.tsx`.

**Step 2:**

Create file `knip.jsonc`

knip.jsonc

    
    
    {
      "$schema": "https://unpkg.com/knip@5/schema-jsonc.json",
      "paths": {
        "src/*": ["./src/*"],
      },
      "project": ["src/**/*.{js,cjs,mjs,jsx,ts,cts,mts,tsx}"],
      "ignoreExportsUsedInFile": true,
      "ignoreDependencies": [
        // ignore dependencies
        "@fontsource.+",
      ],
      "ignore": [
        // ignore folders or files
        "src/_mock/**",
      ],
    }
     

**Step 3:**

Find and delete related files.

Run:

    
    
    npx knip

  
Result:

    
    
    Unused dependencies (10)
    @emotion/styled               package.json
    @fullcalendar/core            package.json
    @tiptap/core                  package.json
    @tiptap/extension-code-block  package.json
    @tiptap/pm                    package.json
    apexcharts                    package.json
    embla-carousel                package.json
    mapbox-gl                     package.json
    react-dom                     package.json
    stylis                        package.json
    Unused devDependencies (1)
    eslint  package.json
    Unlisted binaries (3)
    eslint    package.json
    next      package.json
    prettier  package.json
    Configuration hints (3)

* * *

###### Reference:

  * <https://knip.dev/overview/getting-started>



### dependencies - https://docs.minimals.cc/dependencies

# Dependencies

Based on the provided dependency table you can remove or install the
dependencies you want to use.

* * *
    
    
    # core
    react
    react-dom
    @emotion/cache
    @emotion/react
    @emotion/styled
    @mui/lab
    @mui/material
    @mui/x-data-grid
    @mui/x-tree-view
    @mui/x-date-pickers
     
    # next.js
    "next"
    "@mui/material-nextjs"
     
    # router (vite.js)
    history
    react-router
    react-router-dom
     
    # fonts
    @fontsource/barlow
    @fontsource/dm-sans
    @fontsource/inter
    @fontsource/nunito-sans
    @fontsource/public-sans
     
    # progress bar when change router
    "nprogress"
     
    # drop and drag
    @dnd-kit/core
    @dnd-kit/sortable
    @dnd-kit/utilities
     
    # auth
    firebase
    aws-amplify
    @auth0/auth0-react
    @supabase/supabase-js
     
    # fullcalendar
    @fullcalendar/core
    @fullcalendar/daygrid
    @fullcalendar/interaction
    @fullcalendar/list
    @fullcalendar/react
    @fullcalendar/timegrid
    @fullcalendar/timeline
     
    # icon
    @iconify/react
     
    # pdf
    @react-pdf/renderer
     
    # editor
    @tiptap/core
    @tiptap/extension-code-block
    @tiptap/extension-code-block-lowlight
    @tiptap/extension-image
    @tiptap/extension-link
    @tiptap/extension-placeholder
    @tiptap/extension-text-align
    @tiptap/pm
    @tiptap/react
    @tiptap/starter-kit
    lowlight
     
    # markdown
    react-markdown
    turndown
    rehype-raw
    remark-gfm
    rehype-highlight
     
    # chart
    apexcharts
    react-apexcharts
     
    # format date
    dayjs
     
    # carousel
    embla-carousel
    embla-carousel-auto-height
    embla-carousel-auto-scroll
    embla-carousel-autoplay
    embla-carousel-react
     
    # animation
    framer-motion
     
    # localization
    i18next
    react-i18next
    i18next-resources-to-backend
    i18next-browser-languagedetector
     
    # mapbox
    mapbox-gl
    react-map-gl
     
    # upload
    react-dropzone
     
    # walktour
    react-joyride
     
    # image
    react-lazy-load-image-component
     
    # organizational chart
    react-organizational-chart
     
    # input format
    react-phone-number-input
    mui-one-time-password-input
    autosuggest-highlight
     
    # scrollbar
    simplebar-react
     
    # snackbar
    sonner
     
    # right-to-left
    stylis
    stylis-plugin-rtl
     
    # fetch api
    swr
    axios
     
    # lightbox
    yet-another-react-lightbox
     
    # form validation
    zod
    react-hook-form
    @hookform/resolvers

* * *

#### Eslint

JSTS

    
    
    eslint
    eslint-config-airbnb
    eslint-config-prettier
    eslint-import-resolver-alias
    eslint-plugin-import
    eslint-plugin-jsx-a11y
    eslint-plugin-perfectionist
    eslint-plugin-prettier
    eslint-plugin-react
    eslint-plugin-react-hooks
    eslint-plugin-unused-imports



### tailwind - https://docs.minimals.cc/tailwind

# Integration Tailwind

* * *

##### Install Tailwind CSS

    
    
    npm install -D tailwindcss postcss autoprefixer

* * *

##### Create files

Create files in the root directory

  * `tailwind.config.js`
  * `postcss.config.js` or `postcss.config.cjs` (vite.js)

    
    
    const config = {
      content: ['./index.html', './src/**/*.{js,ts,jsx,tsx}'],
      theme: {
        extend: {},
      },
      corePlugins: {
        // Remove the Tailwind CSS preflight styles so it can use Material UI's preflight instead (CssBaseline).
        preflight: false,
      },
      plugins: [],
    };
     
    export default config;

tailwind.config.js  

    
    
    module.exports = {
      plugins: {
        tailwindcss: {},
        autoprefixer: {},
      },
    }

postcss.config.js

* * *

##### Update file

  * `src/global.css`

    
    
    ...
    /* scrollbar */
    @import 'simplebar-react/dist/simplebar.min.css';
     
    @tailwind base;
    @tailwind components;
    @tailwind utilities;
     
    html {
      ...
    }

src/global.css

* * *

###### Reference:

  * <https://tailwindcss.com/docs/guides/vite>
  * <https://github.com/mui/material-ui/tree/master/examples/material-ui-cra-tailwind-ts>



