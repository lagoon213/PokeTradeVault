# Pokemon Data

## Pokemon Management

System for storing and managing Pokemon in user vaults.

## Pokemon Attributes

### Core Attributes
- **Species**: Pokemon species (e.g., Pikachu, Charizard)
- **Level**: Current level (1-100)
- **Nature**: Pokemon nature (affects stats)
- **Ability**: Pokemon ability
- **Gender**: Male, Female, or Genderless

### Battle Stats
- **IVs (Individual Values)**:
  - HP: 0-31
  - Attack: 0-31
  - Defense: 0-31
  - Sp. Attack: 0-31
  - Sp. Defense: 0-31
  - Speed: 0-31

- **EVs (Effort Values)**:
  - HP: 0-252
  - Attack: 0-252
  - Defense: 0-252
  - Sp. Attack: 0-252
  - Sp. Defense: 0-252
  - Speed: 0-252
  - Total: max 510

### Movesets
- Up to 4 moves per Pokemon
- Move name and type
- PP (Power Points) information

### Special Attributes
- **Shiny**: Boolean flag for shiny Pokemon
- **Hidden Ability**: Boolean for hidden ability
- **Held Item**: Current held item (optional)
- **Origin Game**: Game the Pokemon is from
- **OT (Original Trainer)**: Original trainer name

## Vault Management

### Adding Pokemon
- Manual entry of all attributes
- Import from game data (future)
- Validation of all data fields
- Duplicate detection (warning)

### Organizing Pokemon
- Filter by species, type, level, etc.
- Sort by various attributes
- Tag system for custom organization
- Search functionality

### Trade Availability
- Mark Pokemon as "for trade" or "not for trade"
- Cannot trade Pokemon in active trades
- Cannot trade Pokemon marked as "favorite"

## Data Validation

### Species Validation
- Must be valid Pokemon species
- Reference official Pokemon database
- Support for all generations (configurable)

### Stat Validation
- IVs within valid range (0-31)
- EVs within valid range and total limit
- Level appropriate for species
- Moves must be learnable by species

### Business Rules
- Cannot have duplicate Pokemon in vault (warning only)
- Maximum vault size: 1000 Pokemon (configurable)
- Deleted Pokemon moved to trash (recoverable for 30 days)

## Pokemon Data Source

### Official Data Integration
- Use PokeAPI or similar for species data
- Validate moves, abilities against official data
- Keep data synchronized with game updates

### Custom Data
- User notes on Pokemon
- Custom tags and categories
- Trade history for each Pokemon

## Future Features

- Breeding calculator
- Team builder integration
- Competitive analysis
- Living Dex tracker
- Shiny hunting tracker

## Related Documents

- [[Data Model]] - Pokemon entity structure
- [[API Design]] - Pokemon endpoints
- [[Trade System]] - Pokemon trading mechanics
