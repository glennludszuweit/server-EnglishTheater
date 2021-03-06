# Model

## Company

```javascript
  aboutUs: String,
  owners: [
    {
      position: String,
      bio: String,
      email: String
    }
  ],
  casts: [
    {
      image: String,
      name: String,
      bio: String,
      email: String
    }
  ],
  mission: String,
  supportUs: {
    message: String,
    bankName: String,
    accountHolder: String,
    iban: String,
    bic: String,
  },
  partners: [
    {
      image: String,
      url: String
    }
  ],
```

## User

```javascript
  name: String,
  image: String,
  email: String,
  address: String,
  bio: String,
  role: {
    type: String,
    enum: [
      'admin', //manage and access everything
      'author', //manage blog and articles
      'moderator', //manage couses and show
      'regular' // for future costumers
    ]
    default: 'regular'
  },
  courses: [
    {
      type: mongoose.Schema.Types.ObjectId,
      ref: 'Course'
    }
  ],
  shows: [
    {
      type: mongoose.Schema.Types.ObjectId,
      ref: 'Show'
    }
  ]
```

## Course

```javascript
  category: {
    type: String,
    enum: [
      'weekly courses',
      'online workshops',
      'holiday workshops',
      'school workshops'
    ]
  },
  media: String,
  ageGroup: String,
  description: String,
  location: String,
  dateTime: String,
  price: String,
  moreInfo: String
  termsAndConditions: String
```

## Show

```javascript
  title: String,
  image: String,
  description: String,
  casts: [
    {
      name: String,
      role: String
    }
  ],
  dateTime: String,
  location: String
```

## Blog

```javascript
  title: String,
  author: String,
  image: String,
  content: String
```

## Article

```javascript
  title: String,
  author: String,
  image: String,
  content: String,
  url: String
```

## Announcement

```javascript
  message: String,
  category: {
    type: String,
    enum: [
      'general',
      'courses',
      'shows',
      'blog',
      'articles
    ]
  },
  url: String,
```
