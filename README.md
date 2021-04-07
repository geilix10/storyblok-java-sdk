# Storyblok Java SDK - 1.0

## TL;DR
This is a Java SDK/Wrapper around (yet only) the Storyblok Delivery API. 
### Version 1.0
* Added Storyblok Delivery API for fetching stories.
  * Fetch a single story with a `StoryblokQueryBuilder` and a custom content object or without.
  * Fetch multiple stories with a `StoryblokQueryBuilder` and a custom content object or without.
* Storyblok Richtext-Resolver is now marked as `//Todo Refactor`

# What is Storyblok?
* Website: https://www.storyblok.com

#Installation


#Examples And Usage
## Initialize Storyblok SDK
``
Storyblok client = new Storyblok("YOUR_API_KEY");
``

## Usage
You can make use of the following methods.

`client.fetchStory(String fullSlugOrIdOrUUID)`

`client.fetchStory(String fullSlugOrIdOrUUID, Class<T> contentType)`

`client.fetchStory(String fullSlugOrIdOrUUID, StoryblokQuery query)`

`client.fetchStory(String fullSlugOrIdOrUUID, StoryblokQuery query, Class<T> type)`

`client.fetchStories(StoryblokQuery query)`

`client.fetchStories(StoryblokQuery query, Class<T> contentType)`

## Examples
```java
//Fetch a single story with a custom content object
Story<CustomStoryContent> story = client.fetchStory("home",CustomStoryContent.class);

//Or with a custom query
Story<Map<String,Object>> story = client.fetchStory("home",StoryblokQuery.StoryblokQueryBuilder.newBuilder()
.version(StoryVersion.published)
.build());

//Fetch multiple Stories
Stories<Map<String,Object>> story = client.fetchStories(StoryblokQuery.StoryblokQueryBuilder.newBuilder()
                .startsWith("h")
                .build());
```

#~~Version 0.0.1 - deprecated~~

## ~~How to use?~~
~~Just include the class in src folder and use it like:~~
``RichTextResolver.resolveTextOfEntry(<textToResolve>);``

## ~~Example~~
~~If you retrieve a "blok" from the Storyblok API you can pass the `text` field into the above method. 
You can see a static JSON Example in the test files.~~ 
