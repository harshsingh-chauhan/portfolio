# Data Models: Initial Portfolio Build

This document outlines the primary data structures used within the application. These are not database models but rather TypeScript interfaces that define the shape of the data objects used to populate the UI components.

## 1. Project

Represents a single portfolio project showcased in the "Projects" section.

**Fields**:
- `id` (string): A unique identifier (e.g., 'p1').
- `title` (string): The title of the project.
- `description` (string): A short, one-sentence description.
- `longDescription` (string): A more detailed description for a project page or modal.
- `technologies` (string[]): An array of strings listing the tech stack (e.g., ['React', 'Node.js']).
- `features` (string[]): An array of strings listing key features.
- `image` (string): The path or URL to the project's cover image.
- `liveUrl` (string, optional): The URL to the live deployed version.
- `githubUrl` (string): The URL to the source code on GitHub.
- `featured` (boolean): Whether the project should be highlighted.
- `category` ('frontend' | 'fullstack' | 'backend' | 'tool'): The category of the project for filtering.
- `completionDate` (string): The date the project was completed (e.g., '2024-08-15').

**Example**:
```typescript
interface Project {
  id: string;
  title: string;
  description: string;
  longDescription: string;
  technologies: string[];
  features: string[];
  image: string;
  liveUrl?: string;
  githubUrl: string;
  featured: boolean;
  category: 'frontend' | 'fullstack' | 'backend' | 'tool';
  completionDate: string;
}
```

## 2. Skill

Represents a single technical skill in the "Skills" section.

**Fields**:
- `id` (string): A unique identifier (e.g., 's1').
- `name` (string): The name of the skill (e.g., 'TypeScript').
- `category` ('language' | 'frontend' | 'backend' | 'tool'): The category for filtering.
- `icon` (string): The name of the icon component to use from a library like React Icons.
- `proficiency` ('beginner' | 'intermediate' | 'advanced'): The developer's proficiency level.
- `yearsOfExperience` (number, optional): The number of years of experience with the skill.

**Example**:
```typescript
interface Skill {
  id: string;
  name: string;
  category: 'language' | 'frontend' | 'backend' | 'tool';
  icon: string;
  proficiency: 'beginner' | 'intermediate' | 'advanced';
  yearsOfExperience?: number;
}
```

## 3. TimelineEntry (Experience)

Represents a single entry in the professional or academic timeline.

**Fields**:
- `id` (string): A unique identifier.
- `type` ('work' | 'education' | 'achievement'): The type of entry.
- `title` (string): The job title, degree, or achievement name.
- `organization` (string): The company, university, or issuing body.
- `duration` (string): The date range (e.g., 'June 2024 - August 2024').
- `logo` (string, optional): Path to the organization's logo.
- `description` (string): A description of the role or event.
- `achievements` (string[]): A list of key achievements or bullet points.
- `skills` (string[], optional): Skills used or gained.
- `link` (string, optional): A link for verification or more info.

**Example**:
```typescript
interface TimelineEntry {
  id: string;
  type: 'work' | 'education' | 'achievement';
  title: string;
  organization: string;
  duration: string;
  logo?: string;
  description: string;
  achievements: string[];
  skills?: string[];
  link?: string;
}
```

## 4. BlogPost

Represents a single blog post in the "Blog" section.

**Fields**:
- `id` (string): A unique identifier.
- `title` (string): The title of the article.
- `excerpt` (string): A short preview of the content.
- `content` (string, optional): The full Markdown content of the post.
- `coverImage` (string): Path to the cover image.
- `category` ('react' | 'nodejs' | 'dsa' | 'career' | 'tutorial'): The category for filtering.
- `readTime` (number): Estimated reading time in minutes.
- `publishDate` (string): The date of publication.
- `slug` (string): The URL-friendly slug for the post.
- `tags` (string[]): An array of relevant tags.

**Example**:
```typescript
interface BlogPost {
  id: string;
  title: string;
  excerpt: string;
  content?: string;
  coverImage: string;
  category: 'react' | 'nodejs' | 'dsa' | 'career' | 'tutorial';
  readTime: number;
  publishDate: string;
  slug: string;
  tags: string[];
}
```

## 5. ContactFormData

Represents the data structure for the contact form submission.

**Fields**:
- `name` (string): The sender's name.
- `email` (string): The sender's email address.
- `subject` (string, optional): The subject of the message.
- `message` (string): The content of the message.

**Validation Rules**:
- `name`: required, min 2 chars, max 50 chars.
- `email`: required, must be a valid email format.
- `subject`: optional, max 100 chars.
- `message`: required, min 10 chars, max 500 chars.
