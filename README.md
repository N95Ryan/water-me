# Water Me

A PWA to help you stay hydrated throughout the day.

## Features

- 🔔 Hydration reminder notifications
- 📱 Mobile-optimized responsive interface
- 🔐 Supabase authentication
- 💾 User preferences saving
- ⚡ Optimized performance

## Installation

1. Clone the repository:

```bash
git clone https://github.com/your-username/water-me.git
cd water-me
```

2. Install dependencies:

```bash
npm install
```

3. Create a `.env` file in the project root and add your Supabase environment variables:

```env
PUBLIC_SUPABASE_URL=your_supabase_url
PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
```

4. Start the development server:

```bash
npm run dev
```

## Database Configuration

In your Supabase project, create a `user_preferences` table with the following structure:

```sql
create table user_preferences (
  id uuid default uuid_generate_v4() primary key,
  user_id uuid references auth.users not null,
  daily_goal integer not null,
  reminder_interval integer not null,
  created_at timestamp with time zone default timezone('utc'::text, now()) not null,
  updated_at timestamp with time zone default timezone('utc'::text, now()) not null
);
```

## Technologies Used

- [Astro](https://astro.build)
- [Tailwind CSS](https://tailwindcss.com)
- [Supabase](https://supabase.com)
- [Web Push API](https://developer.mozilla.org/en-US/docs/Web/API/Push_API)

```sh
yarn create astro@latest -- --template basics
```

[![Open in StackBlitz](https://developer.stackblitz.com/img/open_in_stackblitz.svg)](https://stackblitz.com/github/withastro/astro/tree/latest/examples/basics)
[![Open with CodeSandbox](https://assets.codesandbox.io/github/button-edit-lime.svg)](https://codesandbox.io/p/sandbox/github/withastro/astro/tree/latest/examples/basics)
[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/withastro/astro?devcontainer_path=.devcontainer/basics/devcontainer.json)

> 🧑‍🚀 **Seasoned astronaut?** Delete this file. Have fun!

![just-the-basics](https://github.com/withastro/astro/assets/2244813/a0a5533c-a856-4198-8470-2d67b1d7c554)

## 🚀 Project Structure

Inside of your Astro project, you'll see the following folders and files:

```text
/
├── public/
│   └── favicon.svg
├── src/
│   ├── layouts/
│   │   └── Layout.astro
│   └── pages/
│       └── index.astro
└── package.json
```

To learn more about the folder structure of an Astro project, refer to [our guide on project structure](https://docs.astro.build/en/basics/project-structure/).

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

| Command                | Action                                           |
| :--------------------- | :----------------------------------------------- |
| `yarn install`         | Installs dependencies                            |
| `yarn dev`             | Starts local dev server at `localhost:4321`      |
| `yarn build`           | Build your production site to `./dist/`          |
| `yarn preview`         | Preview your build locally, before deploying     |
| `yarn astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `yarn astro -- --help` | Get help using the Astro CLI                     |

## 👀 Want to learn more?

Feel free to check [our documentation](https://docs.astro.build) or jump into our [Discord server](https://astro.build/chat).
