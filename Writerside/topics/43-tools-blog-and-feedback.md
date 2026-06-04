# Internal blog and feedback

## Internal blog

| Route | Template | Purpose |
|-------|----------|---------|
| `/internal-blog` | `internalBlogList` | Post list |
| `/internal-blog/new` | `internalBlogEditor` | Create post |
| `/internal-blog/edit/:_id` | `internalBlogEditor` | Edit post |
| `/internal-blog/:_id` | `internalBlogItem` | Read post |

### List table columns

| Column | Description |
|--------|-------------|
| Created | Date |
| Title | Post title |
| Author | Author |
| Project | Project tag |
| Release Version | Release |
| Tags | Labels |
| Read Status | Read/unread for current user |

| Action | Purpose |
|--------|---------|
| New Post | Create |
| Advanced Filters / Clear Filters | List filtering |
| Edit / Delete | Author or superuser |

Detail pane may show post summary beside the table.

## Feedback and issues

**Route:** `/admin/feedback`  
**Template:** `feedbackAdmin`

Linear / Trello-style task table for internal issue tracking.

| Column (typical) | Description |
|------------------|-------------|
| Task | Title |
| Project | Project |
| Description | Body |
| User | Reporter |
| Priority | Priority |
| Assigned / Start / End Date | Scheduling |
| Duration | Time spent |
| Status | Workflow state |

| Action | Purpose |
|--------|---------|
| Refresh | Reload table |
| Update | Bulk update from modal |
