# SocialCipher

SocialCipher is a decentralized social media platform implemented as a smart contract on the Stacks blockchain. It provides core social networking features while maintaining transparency and user control through blockchain technology.

---

## Features

### User Profiles
- Create and manage user profiles with customizable usernames and bios
- Follow/unfollow functionality
- Token balance tracking
- Admin role support

### Content Management
- Create and view posts (up to 280 characters)
- Comment on posts
- Like posts
- Content moderation through a flagging system

### Moderation System
- Community-driven content flagging
- Automated content flagging threshold (>5 flags)
- Admin-controlled content removal
- Hierarchical admin management

---

## Smart Contract Functions

### User Management
| Function | Parameters | Description |
|----------|------------|-------------|
| `create-profile` | `username: string-utf8, bio: string-utf8` | Create a new user profile |
| `follow-user` | `user-to-follow: principal` | Follow another user |
| `get-profile` | `user: principal` | Retrieve user profile information |

### Content Management
| Function | Parameters | Description |
|----------|------------|-------------|
| `create-post` | `content: string-utf8` | Create a new post |
| `like-post` | `post-id: uint` | Like a post |
| `add-comment` | `post-id: uint, content: string-utf8` | Comment on a post |
| `get-post` | `post-id: uint` | Retrieve post details |
| `get-comment` | `comment-id: uint` | Retrieve comment details |
| `get-post-comments` | `post-id: uint` | Retrieve all comments for a post |

### Moderation
| Function | Parameters | Description |
|----------|------------|-------------|
| `flag-post` | `post-id: uint` | Flag a post for review |
| `flag-comment` | `comment-id: uint` | Flag a comment for review |
| `remove-flagged-post` | `post-id: uint` | Admin removes a flagged post |
| `remove-flagged-comment` | `comment-id: uint` | Admin removes a flagged comment |

### Administration
| Function | Parameters | Description |
|----------|------------|-------------|
| `add-admin` | `user: principal` | Add a new admin |
| `remove-admin` | `user: principal` | Remove an admin |
| `is-admin` | `user: principal` | Check if user is an admin |

---

## Technical Specifications

### Post Limitations
- Maximum content length: 280 characters
- Maximum comments per post: 100
- Automatic flagging at 5+ flags

### Profile Limitations
- Username max length: 30 characters
- Bio max length: 160 characters
- Maximum following/followers: 1000 users

### Error Codes
| Code | Description |
|------|-------------|
| u1 | Profile already exists |
| u11 | Username must not be empty |
| u12 | Content must not be empty |
| u13 | Post not found |
| u14 | Can't follow yourself |
| u15 | Comment content must not be empty |
| u16 | Post not found for comment |
| u20-29 | Various admin and moderation errors |

---

## Security Features
- Contract owner controls admin appointments
- Only admins can remove flagged content
- Built-in protection against self-following
- Automated content flagging system
- User limits to prevent spam and abuse

---

## Token System
The platform includes a native fungible token (`SocialCipher-token`) for future platform features and governance.

---

## Getting Started
1. Deploy the smart contract to your chosen Stacks network
2. Create a user profile using `create-profile`
3. Start engaging with content through posts, comments, and likes
4. Follow other users to build your network

---

## Administration
- Contract owner is set during deployment
- Only the contract owner can appoint/remove admins
- Admins have special privileges for content moderation
- Admin status can be verified using the `is-admin` function

---

## Future Considerations
- Token utility implementation
- Advanced content moderation features
- Enhanced profile customization
- Direct messaging system
- Content encryption features

---

## Contributing
The smart contract is open for review and improvement suggestions. Ensure any proposed changes maintain the security and efficiency of the platform.
