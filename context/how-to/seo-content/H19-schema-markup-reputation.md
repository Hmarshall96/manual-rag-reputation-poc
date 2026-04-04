---
id: H19
title: How to Implement Schema Markup for Reputation
type: how-to
category: seo-content
parent_actions: [A09]
---

# How to Implement Schema Markup for Reputation

Schema markup is structured data that you add to web pages to help search engines understand the content more precisely. For reputation management, schema markup can enhance how a client appears in search results by triggering rich snippets, knowledge panels, and other visual elements that make positive results more prominent and clickable. This guide explains which schema types matter for reputation and how to implement them.

## Why Schema Markup Matters for Reputation

When search engines understand the entities on a page (a person, a company, an article, a review), they can present that information in enhanced formats. A search result with a photo, star rating, or detailed snippet takes up more visual space and attracts more clicks than a plain blue link. In reputation management, this is valuable for two reasons:

1. **Enhanced positive results** draw more clicks, which reinforces their ranking position.
2. **Richer search results** push other results (including negative ones) further down the page visually, even without changing their actual ranking position.

## Key Schema Types for Reputation

Schema.org defines hundreds of types, but only a handful are directly relevant to reputation work. Focus on these.

### Person Schema

Use this on pages about an individual client, such as their personal website, bio page, or About page.

Key properties to include:

- **name** - The person's full name as they want it to appear in search
- **jobTitle** - Their current professional title
- **worksFor** - The organization they are associated with
- **image** - URL of a professional headshot
- **description** - A short professional biography
- **sameAs** - An array of URLs for their official social media profiles (LinkedIn, Twitter, personal website). This helps Google connect all of these properties to the same entity and can contribute to Knowledge Panel generation.

### Organization Schema

Use this on company websites, particularly on the homepage and About page.

Key properties:

- **name** - The official company name
- **logo** - URL of the company logo
- **url** - The official website URL
- **sameAs** - Array of official social media profile URLs
- **foundingDate** - When the company was established
- **description** - A concise description of what the company does
- **address** - Physical address if applicable
- **contactPoint** - Customer service or general contact information

### Article Schema

Apply this to blog posts, news articles, and any editorial content published as part of a reputation strategy.

Key properties:

- **headline** - The article title
- **author** - The author's name (link to Person schema if on the same site)
- **datePublished** - Publication date in ISO 8601 format
- **dateModified** - Last update date
- **image** - Featured image URL
- **publisher** - The publishing organization

### Review Schema

Review schema can generate star ratings in search results, which are visually impactful and increase click-through rates.

Key properties:

- **itemReviewed** - The entity being reviewed
- **reviewRating** - The rating value and scale
- **author** - Who wrote the review
- **reviewBody** - The text of the review

Note: Google has strict guidelines about self-serving reviews. Review schema should only be used for legitimate third-party reviews. Misuse can result in a manual action penalty.

### FAQPage Schema

FAQ schema can generate expandable question-and-answer results in search, taking up significant visual space.

Key properties:

- **mainEntity** - An array of Question entities
- Each Question contains **name** (the question text) and **acceptedAnswer** with **text** (the answer)

This is particularly useful on client websites where you can add a frequently asked questions section addressing common queries about the brand or person.

## Implementing JSON-LD

Google's preferred format for structured data is JSON-LD (JavaScript Object Notation for Linked Data). It is added as a script block in the HTML head section and does not affect the visible page content.

### Person Schema Example

```json
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "Jane Doe",
  "jobTitle": "Chief Executive Officer",
  "worksFor": {
    "@type": "Organization",
    "name": "Example Ltd"
  },
  "image": "https://www.example.com/images/jane-doe.jpg",
  "description": "Jane Doe is the CEO of Example Ltd, a technology consultancy based in London.",
  "sameAs": [
    "https://www.linkedin.com/in/janedoe",
    "https://twitter.com/janedoe",
    "https://www.example.com"
  ]
}
</script>
```

### Organization Schema Example

```json
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Example Ltd",
  "url": "https://www.example.com",
  "logo": "https://www.example.com/images/logo.png",
  "foundingDate": "2010-03-15",
  "description": "Example Ltd is a technology consultancy specializing in digital transformation.",
  "sameAs": [
    "https://www.linkedin.com/company/example-ltd",
    "https://twitter.com/exampleltd",
    "https://www.facebook.com/exampleltd"
  ],
  "contactPoint": {
    "@type": "ContactPoint",
    "telephone": "+44-20-1234-5678",
    "contactType": "customer service"
  }
}
</script>
```

### FAQPage Schema Example

```json
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "What services does Example Ltd provide?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Example Ltd provides digital transformation consulting, software development, and IT strategy services to enterprise clients across Europe."
      }
    },
    {
      "@type": "Question",
      "name": "Who is the CEO of Example Ltd?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Jane Doe has served as CEO of Example Ltd since 2015, bringing over 20 years of experience in the technology sector."
      }
    }
  ]
}
</script>
```

## Adding Schema to WordPress Sites

For reputation client sites built on WordPress, there are several ways to add schema markup.

### Using SEO Plugins

**Yoast SEO** automatically generates basic Organization and Article schema. The premium version allows more detailed schema configuration. Navigate to SEO > Search Appearance > Content Types to configure default schema types for posts and pages.

**RankMath** offers more granular schema control in its free version. Each post and page has a Schema tab in the editor where you can select the schema type and fill in properties. RankMath supports Person, Organization, Article, FAQPage, and many other types out of the box.

### Manual JSON-LD Insertion

If plugins do not provide enough control, add JSON-LD manually:

1. Use a plugin like "Insert Headers and Footers" to add site-wide schema to the head section.
2. For page-specific schema, use a custom field or a code snippet plugin to inject JSON-LD on individual pages.
3. In a custom theme, add the script block directly to the relevant template files using `wp_head` action hooks.

### Dedicated Schema Plugins

**Schema Pro** and **WP Schema** are plugins specifically designed for structured data management. They provide a visual interface for configuring schema on a per-page or per-post-type basis.

## Testing Your Schema Implementation

Always validate structured data after implementation.

### Google Rich Results Test

Visit [https://search.google.com/test/rich-results](https://search.google.com/test/rich-results) and enter the page URL. This tool shows which rich result types are detected and flags any errors or warnings.

### Schema Markup Validator

The Schema.org validator at [https://validator.schema.org](https://validator.schema.org) checks whether your markup conforms to the Schema.org specification, regardless of Google-specific requirements.

### Google Search Console

After schema is live, monitor the Enhancements section in Google Search Console. It reports on detected structured data types across the site and flags any issues that prevent rich results from appearing.

## Impact on Reputation Management

Well-implemented schema markup delivers several reputation benefits:

- **Knowledge Panels** - Person and Organization schema, combined with consistent sameAs links, increases the likelihood of triggering a Knowledge Panel in search results. A Knowledge Panel is a powerful reputation asset because it occupies significant space on the right side of desktop search results.
- **Rich Snippets** - Star ratings, FAQ expandables, and author information make positive results more visually prominent and clickable.
- **Entity Association** - Schema helps Google understand that a person is connected to specific organizations, roles, and achievements, strengthening the positive narrative in search.

## Ongoing Maintenance

Schema markup is not a set-and-forget task. Review and update it when:

- The client changes roles, companies, or contact information.
- New social profiles are created that should be linked via sameAs.
- New content types are published that need their own schema.
- Google updates its structured data guidelines or supported types.

Regular testing ensures that schema continues to generate the intended rich results and that no errors have been introduced by site updates or plugin changes.
