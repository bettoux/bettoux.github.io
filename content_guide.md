# Content Management Guide

This guide explains how to update the website content easily without touching the code.

## Overview

The Facettes website now uses a separate content management system that allows non-technical users to update website content by editing JSON files instead of modifying HTML code directly.

## Content Structure

Website content is stored in JSON files located in the `content/` directory:

- `content/en.json` - English content
- `content/fr.json` - French content

## How to Update Content

### 1. Text Content

To update any text on the website:

1. Open the appropriate language file (`en.json` for English, `fr.json` for French)
2. Find the key that corresponds to the content you want to change
3. Update the value (the text after the colon)
4. Save the file

**Example**: To change the hero tagline in English:
```json
"hero_tagline": "Your New Tagline Here"
```

### 2. Speaker Information

Speaker data is stored in the `speakers` section of each language file. Each speaker has:

- `name`: Speaker's full name
- `title`: Professional title/role
- `bio_long`: Detailed biography for the speaker detail page
- `focus`: Array of expertise areas
- `image_url`: URL to speaker's photo

**Example**: To add a new speaker:
```json
"speakers": {
  "existing_speaker": { ... },
  "new_speaker_id": {
    "name": "Dr. Jane Smith",
    "title": "Innovation Expert",
    "bio_long": "Dr. Jane Smith is a renowned innovation expert...",
    "focus": ["Innovation Strategy", "Digital Transformation", "Leadership"],
    "image_url": "https://example.com/jane-smith-photo.jpg"
  }
}
```

### 3. Services Information

Service cards can be updated by modifying:
- `service_1_title`, `service_2_title`, `service_3_title`: Service names
- `service_1_description`, `service_2_description`, `service_3_description`: Service descriptions

### 4. Form Labels and Messages

All form fields, buttons, and messages can be updated by finding their corresponding keys in the JSON files.

## Content Keys Reference

### Navigation
- `nav_speakers`, `nav_services`, `nav_contact`: Main navigation items
- `nav_speakers_mobile`, `nav_services_mobile`, `nav_contact_mobile`: Mobile navigation

### Hero Section
- `hero_tagline`: Main headline
- `hero_subheading`: Subtitle text
- `hero_cta`: Call-to-action button text

### Speakers Section
- `speakers_heading`: Section title
- `speakers_subtext`: Section subtitle
- `speaker_1_title`, `speaker_2_title`, `speaker_3_title`: Speaker roles
- `speaker_1_bio_short`, `speaker_2_bio_short`, `speaker_3_bio_short`: Brief descriptions
- `speaker_cta`: Speaker inquiry link text

### Services Section
- `services_heading`: Section title
- `services_subtext`: Section subtitle
- Service cards: `service_[1-3]_title` and `service_[1-3]_description`

### Contact Section
- `contact_heading`: Section title
- `contact_tagline`: Section subtitle
- Form fields: `form_name`, `form_email`, `form_event`, `form_details`
- Buttons: `form_submit`, `form_generate`
- Messages: `contact_response_time`, `output_heading`, etc.

### Speaker Detail Page
- `detail_back`: Back button text
- `detail_focus_areas`: Focus areas section title
- `detail_biography`: Biography section title
- `detail_inquire_cta`: Inquiry button text

### Footer
- `footer_rights`: Copyright text

## Best Practices

1. **Always update both language files**: When updating content, remember to update both `en.json` and `fr.json` files
2. **Maintain JSON formatting**: Ensure proper JSON syntax (quotes, commas, brackets)
3. **Test after changes**: Always check the website after making changes to ensure content displays correctly
4. **Keep consistent tone**: Maintain the professional, premium tone established in the existing content
5. **Backup before major changes**: Keep a copy of the original files before making significant updates

## Adding New Speakers

To add a new speaker to the roster:

1. Choose a unique ID for the speaker (e.g., "maria_gonzalez")
2. Add the speaker data to the `speakers` object in both language files
3. Update the main speakers list in the HTML if you want them to appear on the homepage (this requires code editing)

## Troubleshooting

- **Website shows error message**: Check that JSON files are valid (proper syntax, all quotes and commas in place)
- **Content not updating**: Clear browser cache and refresh the page
- **Missing translations**: Ensure both language files have matching keys
- **Special characters**: Use proper JSON escaping for quotes and special characters

## JSON Validation

Before saving changes, validate your JSON using:
- Online JSON validators (search "JSON validator")
- Code editors with JSON validation features
- Browser developer tools (will show errors in console)

## Getting Help

If you encounter issues or need to add features beyond simple content updates, contact your web developer for assistance.