# Data Model

## Core Entities

### User
- `id`: Unique identifier
- `username`: Display name
- `email`: Contact email
- `password_hash`: Encrypted password
- `created_at`: Account creation timestamp
- `reputation_score`: Trading reputation

### Pokemon
- `id`: Unique identifier
- `user_id`: Owner reference
- `species`: Pokemon species name
- `level`: Pokemon level
- `nature`: Pokemon nature
- `ability`: Pokemon ability
- `moves`: Array of move names
- `ivs`: Individual values (HP, Attack, Defense, etc.)
- `evs`: Effort values
- `is_shiny`: Boolean flag
- `for_trade`: Boolean availability flag

### Trade
- `id`: Unique identifier
- `proposer_id`: User who initiated trade
- `recipient_id`: User receiving trade proposal
- `status`: Trade status (pending, accepted, rejected, completed, cancelled)
- `proposed_at`: Timestamp of proposal
- `completed_at`: Timestamp of completion

### TradeOffer
- `id`: Unique identifier
- `trade_id`: Parent trade reference
- `pokemon_id`: Pokemon being offered
- `side`: Which side of the trade (proposer/recipient)

## Relationships

- User **has many** Pokemon
- User **participates in many** Trades
- Trade **has many** TradeOffers
- TradeOffer **belongs to** Pokemon

## Database Schema Considerations

- Indexes on frequently queried fields (user_id, species, for_trade)
- Foreign key constraints for data integrity
- Soft deletes for audit trail
- Timestamps for all entities

## Related Documents

- [[Architecture]] - System design
- [[Trade System]] - Trade workflow
- [[API Design]] - API endpoints using this model
