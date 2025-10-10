# Ethscriptions Collections Metadata

This repository serves as a central hub for Ethscriptions collection metadata submissions for the floored app. Collection creators can submit their metadata files here, enabling seamless integration with the floored platform.

## Purpose

The repository aims to:
- Provide a standardized way for Ethscriptions collections to submit their metadata
- Enable proper collection display and functionality within the floored app
- Maintain a consistent metadata format across all collections
- Serve as a public resource for builders and developers in the Ethscriptions ecosystem

## Usage

### TypeScript Support

The repository includes TypeScript type definitions for the metadata structure. You can import these types in your project:

```typescript
import { Metadata, CollectionMetadata, CollectionItem, Attribute } from './types';
```

### Example Usage

```typescript
import { CollectionMetadata } from './types';
import collectionMetadata from './metadata/your-collection.json';

// Access collection information
console.log(collectionMetadata.name);
console.log(collectionMetadata.description);

// Access individual items
const firstItem = collectionMetadata.collection_items[0];
console.log(firstItem.name);
console.log(firstItem.attributes);

// Or load dynamically
import fs from 'fs';
const collectionData: CollectionMetadata = JSON.parse(
  fs.readFileSync('./metadata/collection-name.json', 'utf8')
);
```

## Metadata Structure

Each collection metadata file follows this structure:

```typescript
interface CollectionMetadata {
  name: string;
  logo_image: string | null;
  banner_image: string | null;
  total_supply: number;
  slug: string;
  description: string;
  website_url: string | null;
  twitter_url: string | null;
  discord_url: string | null;
  background_color: string | null;
  collection_items: CollectionItem[];
}
```

## How to Submit Your Collection

1. Fork this repository
2. Create your collection metadata file in the `metadata` directory using the format: `your-collection-slug.json`
3. Ensure your metadata follows the TypeScript interface defined above
4. Submit a pull request with your changes

## Validation

Before submitting, please ensure:
- Your JSON file is properly formatted and valid
- All required fields are filled out
- Image URLs are accessible and permanent
- Your collection slug is unique and matches your Ethscriptions collection

## License

This metadata repository is released into the public domain under The Unlicense.

Note: While this metadata structure is released into the public domain, the individual collections maintain their own respective rights and licenses.

## Support

For questions or support:
- Open an issue in this repository
- Follow us on X [@flooredApe](https://twitter.com/flooredApe)