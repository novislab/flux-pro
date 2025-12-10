# Flux Pro

The pro version of Flux, the official UI component library for Livewire.

## Installation

### 1. Install via Composer

Add the GitHub repository to your `composer.json`:

```json
{
    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/novislab/flux-pro"
        }
    ]
}
```

Then require the package:

```bash
composer require livewire/flux-pro
```

Or install directly from the repository:

```bash
composer require livewire/flux-pro:dev-main
```

### 2. Configure Tailwind CSS

Add the Flux Pro styles and component paths to your `app.css`:

```css
@import "tailwindcss";
@import "../../vendor/livewire/flux-pro/dist/flux.css";

@source '../views';
@source '../../vendor/livewire/flux-pro/stubs/**/*.blade.php';
```

### 3. Publish Assets (Optional)

If you need to customize the components, you can publish the views:

```bash
php artisan vendor:publish --tag=flux-pro-views
```

## Usage

Once installed, you can use Flux Pro components in your Blade templates:

```blade
<flux:editor wire:model="content" />

<flux:command placeholder="Search commands...">
    <flux:command.option>Option 1</flux:command.option>
    <flux:command.option>Option 2</flux:command.option>
</flux:command>

<flux:chart>
    <flux:chart.line field="revenue" />
    <flux:chart.axis />
    <flux:chart.legend />
</flux:chart>

<flux:table>
    <flux:table.header>
        <flux:table.heading>Name</flux:table.heading>
        <flux:table.heading>Email</flux:table.heading>
    </flux:table.header>
    <flux:table.body>
        @foreach($users as $user)
            <flux:table.row>
                <flux:table.cell>{{ $user->name }}</flux:table.cell>
                <flux:table.cell>{{ $user->email }}</flux:table.cell>
            </flux:table.row>
        @endforeach
    </flux:table.body>
</flux:table>

<flux:date-picker wire:model="date" />

<flux:time-picker wire:model="time" />

<flux:autocomplete wire:model="selection" />

<flux:file-upload wire:model="files" />

<flux:radio.variants.cards label="Option 1" />

<flux:card>
    <flux:card.header>Card Title</flux:card.header>
    <flux:card.body>Card content goes here</flux:card.body>
</flux:card>
```

## Available Components

Flux Pro includes the following premium components:

- **Editor** - Rich text editor with toolbar
- **Command** - Command palette interface
- **Chart** - Advanced charting with area, line, axis, legend, and tooltip
- **Calendar** - Interactive calendar component
- **Date Picker** - Date selection with calendar
- **Time Picker** - Time selection interface
- **Autocomplete** - Autocomplete input field
- **File Upload** - File upload with drag & drop
- **Table** - Advanced table with pagination support
- **Radio Variants** - Radio buttons in cards, pills, and button styles
- **Checkbox** - Enhanced checkbox components
- **Card** - Card container with variants
- **Select** - Enhanced select dropdown
- **Tab** - Tab navigation
- **Popover** - Popover overlay
- **Accordion** - Collapsible accordion
- **Toast** - Toast notifications
- **Pillbox** - Pill/tag selection interface

## Requirements

- PHP ^8.1
- Laravel ^10.0|^11.0|^12.0
- Livewire ^3.7.0|^4.0
- Flux (base package)