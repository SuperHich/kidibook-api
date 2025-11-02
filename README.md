# Kidibook API 

A JSON Server API that provides personalized children's stories with dynamic name replacement and gender-specific content.

## Features

- **Personalized Stories**: Stories with `{{name}}` placeholders that can be dynamically replaced
- **Gender-Specific Content**: Separate story versions for boys and girls with appropriate pronouns and character names
- **Rich Story Collection**: Multiple story versions (v1, v2, v3) with different themes:
  - Adventure stories (desert, mountain, forest)
  - Fantasy tales (wonderland, magical powers, castle mysteries)
  - Modern adventures (Pac-Man world, racing)
  - Educational stories (animal friends, treasure hunts)
- **Image Support**: Each story includes associated images served statically
- **RESTful API**: Standard JSON Server endpoints for easy integration

## Project Structure

```
kidibook-api/
db.json              # Main database with stories
stories/             # Story versions
v1.json         # First version
v2.json         # Second version  
v3.json         # Latest version
images/             # Story images
package.json        # Dependencies and scripts
README.md          # This file
```
## Quick Start

### Prerequisites
- Node.js (v14 or higher)
- npm

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd kidibook-api
```
2. Install dependencies:
```bash
npm install
```
3. Start the server:
```bash
npm start
```
The API will be available at `http://localhost:3000` (or the port specified by the `$PORT` environment variable).

## API Endpoints

### Stories

- `GET /stories` - Get all stories
- `GET /stories/:id` - Get a specific story by ID
- `POST /stories` - Create a new story
- `PUT /stories/:id` - Update a story
- `DELETE /stories/:id` - Delete a story

### Images

- `GET /images/:filename` - Serve story images statically

## Story Structure

Each story in the database contains:

```json
{
  "id": "unique_story_id",
  "title": "Story Title",
  "image": "images/story_image.jpg",
  "image_girl": "images/story_image_girl.jpg",
  "body": "Story content with {{name}} placeholder...",
  "body_boy": "Boy-specific story version...",
  "body_girl": "Girl-specific story version...",
  "creationDate": "2025-10-19T17:00:00Z"
}
```
### Dynamic Content

- **Name Replacement**: Use `{{name}}` in story content for personalization
- **Gender-Specific Stories**: Stories can have separate `body_boy` and `body_girl` versions
- **Adaptive Pronouns**: Gender-specific versions use appropriate pronouns and character names

## Deployment

The server is configured for deployment with:
- Dynamic port binding (`$PORT` environment variable)
- Host binding to `0.0.0.0` for cloud deployment
- Static file serving for images

### Example deployment commands:
```bash
# For Heroku, Railway, or similar platforms
npm start

# For custom deployment
PORT=8080 npm start
```
## Development

### Adding New Stories

1. Add story data to `db.json` or the appropriate version file in `stories/`
2. Include corresponding images in the `images/` directory
3. Follow the story structure format with proper ID and metadata

### Story Themes Available

- **Adventure**: Desert expeditions, mountain skiing, forest exploration
- **Fantasy**: Magical powers, castle mysteries, wonderland adventures  
- **Modern**: Video game worlds, racing competitions
- **Educational**: Animal communication, treasure hunting, problem-solving

## Configuration

The server uses json-server with the following configuration:
- **Database**: `db.json`
- **Static Files**: `./images` directory
- **Port**: Environment variable `$PORT` or default
- **Host**: `0.0.0.0` for external access

## License

This project is for educational and entertainment purposes, providing personalized storytelling experiences for children.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Add your stories or improvements
4. Submit a pull request

---

*Made with for creating magical storytelling experiences for children*
