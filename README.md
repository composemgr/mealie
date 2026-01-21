# Mealie

Mealie is a self-hosted recipe manager and meal planner with a modern web interface. It allows you to organize recipes, plan meals, generate shopping lists, and share recipes with family and friends.

## Features

- **Recipe Management**: Import, organize, and search recipes
- **Recipe Import**: Automatic import from URLs with schema.org support
- **Meal Planning**: Weekly meal planner with calendar view
- **Shopping Lists**: Automatic shopping list generation from meal plans
- **Multi-User**: Support for multiple users and groups
- **Recipe Sharing**: Share recipes within groups or publicly
- **OCR Support**: Extract recipes from images
- **Nutritional Info**: Track nutritional information
- **Tags & Categories**: Organize with custom tags and categories
- **REST API**: Full API access for integrations
- **Mobile Friendly**: Responsive design for mobile devices

## Installation

### Option 1: Quick Install
```bash
curl -q -LSsf "https://raw.githubusercontent.com/composemgr/mealie/main/docker-compose.yaml" | docker compose -f - up -d
```

### Option 2: Git Clone
```bash
git clone "https://github.com/composemgr/mealie" ~/.local/srv/docker/mealie
cd ~/.local/srv/docker/mealie
docker compose up -d
```

### Option 3: Using composemgr
```bash
composemgr install mealie
```

## Configuration

### Environment Variables

**Database:**
- `DB_USER_NAME`: Database username (default: mealie)
- `DB_USER_PASS`: Database password (default: changeme_db_password)
- `DB_CREATE_DATABASE_NAME`: Database name (default: mealie)

**Email (SMTP):**
- `EMAIL_SERVER_HOST`: SMTP server (default: 172.17.0.1)
- `EMAIL_SERVER_PORT`: SMTP port (default: 587)
- `EMAIL_SERVER_LOGIN_NAME`: SMTP username
- `EMAIL_SERVER_LOGIN_PASS`: SMTP password

**Registration:**
Set `ALLOW_SIGNUP: "false"` to disable public registration after creating admin account.

### Ports

- `9000`: Web interface and API

## Initial Setup

1. Access Mealie at `http://localhost:9000`
2. Create first user account (becomes admin)
3. Configure settings:
   - Site settings (name, language)
   - Group settings
   - Email settings for notifications
4. Disable public signup if desired
5. Import or create your first recipe
6. Set up meal plan for the week

## Recipe Import

### From URL
1. Go to Recipes > New Recipe
2. Enter URL of recipe page
3. Mealie automatically extracts recipe data
4. Review and save

### Manual Entry
Create recipes manually with full control over ingredients, instructions, and metadata.

### Bulk Import
Import recipes in JSON format from other tools.

### OCR (Image to Recipe)
Upload recipe images and extract text using OCR.

## Meal Planning

1. Go to Meal Plan section
2. Drag recipes to calendar days
3. Add breakfast, lunch, dinner, and snacks
4. Generate shopping list from meal plan
5. Check off items as you shop

## Security Recommendations

- **Strong Passwords**: Use strong passwords for all accounts
- **Disable Signup**: Set `ALLOW_SIGNUP: "false"` after initial setup
- **HTTPS**: Use reverse proxy with SSL/TLS
- **Backups**: Regular backups of database and recipe data
- **Network Access**: Restrict access with firewall rules
- **API Tokens**: Protect API tokens and rotate regularly
- **Updates**: Keep Mealie updated for security patches

## Backup

Critical directories to backup:
- `./rootfs/db/postgres/mealie`: Database with recipes and meal plans
- `./rootfs/data/mealie`: Recipe images and attachments

## Advanced Features

### Groups
Create multiple groups for different households or meal planning purposes.

### Cookbooks
Organize recipes into cookbooks for easy access.

### Recipe Notes
Add personal notes and modifications to recipes.

### Shopping Lists
- Create multiple shopping lists
- Share lists with group members
- Organize by categories

### Integrations
Use the REST API to integrate with:
- Home Assistant
- Grocy
- Custom applications

## Troubleshooting

### Recipe Import Failed
- Verify URL contains schema.org recipe markup
- Try manual import if automatic fails
- Check website allows scraping

### Email Not Sending
- Verify SMTP settings are correct
- Test email configuration in settings
- Check SMTP server logs

### Database Connection Issues
- Verify mealie-db container is running
- Check database credentials
- Review PostgreSQL logs

### Images Not Loading
- Check file permissions on data directory
- Verify storage space available
- Review container logs

## Mobile Access

Access Mealie through mobile browser or add as PWA (Progressive Web App):
1. Open in mobile browser
2. Add to home screen
3. Use like native app

## Documentation

- Official Documentation: https://docs.mealie.io/
- GitHub: https://github.com/mealie-recipes/mealie
- Discord Community: https://discord.gg/QuStdQGSGK
- API Documentation: http://localhost:9000/docs (when API_DOCS is enabled)

## License

Mealie is licensed under the GNU AGPL v3.
