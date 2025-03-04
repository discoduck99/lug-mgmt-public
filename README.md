# LUG MGMT - LEGO User Group Management Plugin

A comprehensive WordPress plugin designed specifically for LEGO User Groups (LUGs) to manage activities, track participation, and maintain a points-based engagement system.

![WordPress](https://img.shields.io/badge/WordPress-5.0%2B-blue)  
![PHP](https://img.shields.io/badge/PHP-7.2%2B-purple)  
![Version](https://img.shields.io/badge/Version-1.2.6-green)  
![License](https://img.shields.io/badge/License-GPL--2.0-orange)  

---

## 🚀 Features

### Activity Management
- Create and manage events/activities
- Public and private event support
- Category organization
- Date and time management
- External URL support with clickable titles
- Location tracking (optional)
- Participation tracking types (daily or full event)
- Optional pagination with AJAX loading
- Customizable sorting options

### Member Management
- Automatic numeric username generation
- Member status tracking system
- Registration and dues management
- Comprehensive member profiles including:
  - LEGO-specific profile fields (Bricklink, Rebrickable, LEGO Ideas)
  - Social media integration (including Flickr)
  - Biographical info (1,000 character limit)
  - Custom profile visibility options
- Anonymous feedback submission

### Points System
- Automatic point calculation
- Role-based point assignment
- Manual points assignment
- Registration and dues points tracking
- Year-based tracking
- Member rankings
- Debug logging for calculations

### Dashboard Integration
- "My LUG Participation" widget
- "LUG Points Ranking" widget
- "Membership Status" widget
- Anonymous Feedback Widget
- Year-based filtering
- Real-time statistics updates
- Direct links to participation management
- Loading indicators for stat updates

### Reports & Analytics
- Comprehensive participation reports
- Year-specific reporting with "All Years" option
- Total points calculations
- Member participation history
- Registration and dues status tracking
- Status indicators and filtering
- Bulk action support

---

## 📋 Requirements

- WordPress 5.0 or higher
- PHP 7.2 or higher
- MySQL 5.6 or higher

---

## 💾 Installation

1. Upload the `lug-mgmt` folder to `/wp-content/plugins/`
2. Activate through WordPress plugins menu
3. Configure via the LUG MGMT menu in the admin dashboard

---

## 🔧 Initial Setup

### 1. Categories Setup
Navigate to `Activities > Categories`:

Example Categories:
```markdown
- Workshops (hands-on learning events)
- Presentations (formal talks)
- Social Events (casual meetups)
- Projects (collaborative work)
```

### 2. Role Configuration
Access `LUG MGMT > Roles`:

Example Roles and Points:
```markdown
- Presenter (50 points)
- Helper (25 points)
- Participant (10 points)
- Organizer (40 points)
```

### 3. Activity Creation
Under `Activities > Add New`:

**Required Fields:**
```markdown
- Title
- Start Date
- End Date
- Category
```

**Optional Fields:**
```markdown
- Description
- Start/End Times
- Location
- Organizer
- Private Status
- External URL
```

---

## 🔌 Shortcodes

### [lug_activities]
Displays a list of activities with optional filtering and formatting.

**Parameters:**
| Parameter  | Options              | Default   | Description                    |
|------------|---------------------|-----------|---------------------------------|
| category   | category-slug       | empty     | Filter activities by category   |
| show       | upcoming, past, all | upcoming  | Filter activities by date       |
| private    | true, false         | false     | Include private activities      |
| limit      | number              | 10        | Number of activities to display |
| year       | YYYY                | empty     | Filter activities by year       |
| sort       | asc, desc           | asc       | Sort order by date             |
| paginate   | true, false         | false     | Enable pagination              |

**Example:**
```shortcode
[lug_activities category="meetings" show="upcoming" limit="5" paginate="true" sort="desc"]
```

### [visible_members]
Displays a list of members who have opted to be visible in the directory.

**Parameters:**
| Parameter | Options         | Default       | Description     |
|-----------|----------------|---------------|-----------------|
| orderby   | display_name   | display_name  | Sort field      |
| order     | asc, desc      | asc          | Sort direction  |

**Example:**
```shortcode
[visible_members order="desc"]
```

### [lug_profile]
Displays a member's profile information.

**Parameters:**
| Parameter | Options         | Default      | Description         |
|-----------|----------------|--------------|---------------------|
| user_id   | number         | current user | User ID to display  |

**Example:**
```shortcode
[lug_profile user_id="123"]
```

---

## 📊 Database Structure

### Core Tables
```plaintext
- wp_lug_roles
- wp_lug_participation
- wp_lug_member_status
```

### Custom Post Types
```plaintext
- lug_activity
```

### Taxonomies
```plaintext
- lug_activity_category
```

---

## 🔒 Security Features

- WordPress capability-based access control
- Nonce verification on all forms
- Data sanitization and validation
- Secure storage of sensitive data
- XSS protection

---

## 🛠 Developer Notes

- Native WordPress auto-update support
- GitHub-based plugin update system
- Composer dependency management
- Debug logging capabilities
- Improved date handling and timezone support

---

## 📄 Changelog

For a detailed history of changes, see the [changelog.txt](changelog.txt) file.

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

---

## 📄 License

This project is licensed under the GPL-2.0 License - see the [LICENSE](LICENSE) file for details.

---

## 👥 Support

For support queries:
- Submit [Issues](https://github.com/discoduck99/lug-mgmt/issues)
