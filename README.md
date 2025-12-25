# Moly.hu Spoke for ServiceNow

A custom Integration Hub spoke that connects ServiceNow to the [moly.hu](https://moly.hu) Hungarian book database API.

## Overview

This spoke enables ServiceNow workflows to search, retrieve, and work with book data from moly.hu, Hungary's largest book community and database. All actions include parsed JSON outputs for direct use in Flow Designer, as well as raw response bodies for custom handling.

## Actions

| Action | Description | Key Input |
|--------|-------------|-----------|
| **Book Search** | Search for books by title, author, or keyword | `q` (search query) |
| **ISBN Search** | Look up a book by its ISBN number | `q` (ISBN) |
| **Book Details** | Get full metadata for a specific book | `bookId` |
| **Author** | Get author information | `authorId` |
| **Editions** | List all editions of a book | `bookId` |
| **Ratings** | Get user ratings/reviews for a book | `bookId` |
| **Citations** | Get notable citations from a book | `bookId` |

## Authentication

The spoke uses API key authentication. Configure your API key in the Connection & Credential Alias associated with this spoke. The key is passed as a query parameter (`key`) on all requests and mapped from the associated alias.

## Outputs

Each action provides:
- **Parsed outputs**: Structured data points extracted from the response (book title, authors, cover URL, etc.)
- **Raw JSON**: Complete response body for custom processing

## API Reference

Base URL: `https://moly.hu/api`

For moly.hu API documentation and to request an API key, visit [moly.hu](https://moly.hu).

## Usage Example

Use the **ISBN Search** action in a Flow Designer flow to look up book details from an ISBN number, then use the parsed outputs to create or update records in your book catalog.
