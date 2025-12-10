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
    ],
    "require": {
        "livewire/flux-pro": "dev-main"
    }
}
```

Then run:
```bash
composer update
```

Or install directly:
```bash
composer require livewire/flux-pro:dev-main
```

**Note:** Make sure the package's `composer.json` has `"name": "livewire/flux-pro"` for this to work.

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
{{-- Editor --}}
<flux:editor wire:model="content" />

{{-- Command Palette --}}
<flux:command placeholder="Search commands...">
    <flux:command.option>Option 1</flux:command.option>
    <flux:command.option>Option 2</flux:command.option>
</flux:command>

{{-- Charts --}}
<flux:chart>
    <flux:chart.line field="revenue" />
    <flux:chart.axis />
    <flux:chart.legend />
</flux:chart>

{{-- Tables --}}
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

{{-- Date & Time Pickers --}}
<flux:date-picker wire:model="date" />
<flux:time-picker wire:model="time" />

{{-- Form Components --}}
<flux:autocomplete wire:model="selection" />
<flux:file-upload wire:model="files" />
<flux:radio.variants.cards label="Option 1" />

{{-- Cards --}}
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

## License
This is a public mirror repository. Please refer to the original Flux Pro license terms.
