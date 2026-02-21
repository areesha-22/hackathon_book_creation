# Data Model: ROS 2 Middleware for Humanoid Robotics

## Overview
This document defines the data structures and relationships for the ROS 2 Middleware for Humanoid Robotics module.

## Core Entities

### BookContent
- **id**: UUID (primary key)
- **title**: String (chapter/section title)
- **content**: Text (Markdown content of the chapter)
- **module**: String (module name: "ros2-middleware", "gazebo-unity", "nvidia-isaac", "vla")
- **word_count**: Integer (number of words in content)
- **created_at**: DateTime (timestamp of creation)
- **updated_at**: DateTime (timestamp of last update)
- **version**: String (content version)

### Embedding
- **id**: UUID (primary key)
- **content_id**: UUID (foreign key to BookContent)
- **vector**: Array<Float> (embedding vector from text)
- **chunk_text**: Text (text chunk that was embedded)
- **chunk_index**: Integer (position of chunk in original content)
- **created_at**: DateTime (timestamp of creation)

### ChatSession
- **id**: UUID (primary key)
- **user_id**: UUID (identifier for user session)
- **created_at**: DateTime (timestamp of session creation)
- **last_accessed**: DateTime (timestamp of last interaction)
- **active**: Boolean (whether session is currently active)

### ChatMessage
- **id**: UUID (primary key)
- **session_id**: UUID (foreign key to ChatSession)
- **role**: Enum ("user", "assistant")
- **content**: Text (message content)
- **timestamp**: DateTime (when message was created)
- **sources**: JSON (references to source content that informed the response)

### UserQuery
- **id**: UUID (primary key)
- **session_id**: UUID (foreign key to ChatSession)
- **query_text**: Text (original user query)
- **processed_query**: Text (query after preprocessing)
- **response**: Text (generated response from RAG system)
- **confidence_score**: Float (confidence in response accuracy)
- **retrieved_chunks**: JSON (chunks retrieved from vector store)
- **timestamp**: DateTime (when query was processed)

## Relationships
- BookContent 1 --- * Embedding (one content item can have multiple embeddings)
- ChatSession 1 --- * ChatMessage (one session can have multiple messages)
- ChatSession 1 --- * UserQuery (one session can have multiple queries)
- UserQuery 1 --- * Embedding (queries retrieve from embeddings)

## Validation Rules
- BookContent.title must be 1-200 characters
- BookContent.content must be 100-3000 words (based on spec constraint)
- Embedding.vector must have consistent dimensions (1536 for OpenAI ada-002)
- ChatSession.active defaults to true
- UserQuery.confidence_score must be between 0.0 and 1.0
- All timestamps are in UTC

## State Transitions
- BookContent: draft → reviewed → published → archived
- ChatSession: active → inactive (after 30 minutes of inactivity)