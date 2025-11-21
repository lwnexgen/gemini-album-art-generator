# Copilot Instructions for Gemini Album Art Generator

## Project Overview

This project generates album art for bootleg concert recordings using the Google Gemini API. The system takes concert metadata in JSON format and creates appropriate album artwork.

## Project Purpose

- Generate visually appealing album art for live concert bootlegs
- Process concert metadata including artist, venue, date, and setlist information
- Leverage AI (Gemini) to create context-aware artwork based on concert details

## Input Data Schema

The project works with concert metadata in JSON format with the following key components:

- **artist**: The performing artist name
- **location**: Venue details (city, venue name, nation, state, country code)
- **date**: Concert date (year, month, day)
- **setlist**: Array of tracks with track number, title, disc number, and optional unmatched flag

## Development Guidelines

### Code Organization

- Keep code modular and focused on specific tasks
- Separate data processing, API interaction, and image generation concerns
- Follow clear naming conventions that reflect the music/concert domain

### Data Handling

- Always validate JSON input against the schema defined in README.md
- Handle missing or malformed data gracefully
- Consider edge cases like multi-disc bootlegs or unmatched tracks

### API Integration

- Use Google Gemini API for album art generation
- Implement proper error handling for API calls
- Consider rate limiting and API quota management
- Keep API keys secure and never commit them to the repository

### Image Generation

- Generate high-quality album art suitable for music players
- Consider standard album art dimensions (e.g., 1000x1000, 3000x3000)
- Ensure generated art is appropriate for the concert context

### Testing

- Test with various concert metadata scenarios
- Validate JSON schema compliance
- Test API integration with mock responses when appropriate
- Verify generated images meet quality standards

### Documentation

- Keep README.md updated with usage examples
- Document API requirements and setup instructions
- Include sample JSON files for testing
- Document any configuration options

## Best Practices

- Write clean, readable code with clear variable names
- Add comments for complex logic, especially around API interactions
- Handle errors gracefully with informative messages
- Use environment variables for API keys and configuration
- Consider cost implications of API calls when implementing features
- Optimize prompts sent to Gemini for best results

## Domain Knowledge

- Bootleg recordings are unofficial live concert recordings
- Setlists may vary by disc for multi-disc releases
- Concert metadata may come from various sources with varying quality
- Album art should reflect the live music context, not studio recordings
