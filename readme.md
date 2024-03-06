# Redis Cheatsheet

This repository contains notes and key concepts for learning Redis, based on Redis University courses.

## Keys

- **Unique**: Keys are unique within a Redis database.
- **Binary safe**: Redis keys can be binary safe, meaning they can be any binary sequence.
- **Key size**: Keys can be up to 512MB in size.

### Commands

- `SET`: Set a key's value.
- `EXISTS`: Check if a key exists.
- `GET`: Get a key's value.
- `KEYS`: List all keys.
- `SCAN`: List all keys in a more production-friendly way.
- `DEL`: Delete a key synchronously.
- `UNLINK`: Delete a key asynchronously.
- `FLUSHALL`: Remove all keys.
- `TYPE`: Check the datatype of a key's value.
- `OBJECT`: Check the encoding of a key's value.

### Expiration

- `SET` with `EX` or `PX`: Set an expiration time for a key.
- `PEXPIRE` for existing keys: Set an expiration time for an existing key.
- `TTL` and `PTTL`: Check the remaining time to live of a key.
- `PERSIST`: Remove the expiration time of a key.

## String

- **Common uses**: Storing strings, numerical values, serialized JSON, and binary data.
- **Maximum value size**: 512MB.
- **Content flexibility**: Values can be changed between string, number, binary, or any format for the same key.

### Commands

- `INCR` and `INCRBY`: Increment a key's value.
- `DECR` and `DECRBY`: Decrement a key's value.
- `INCRBYFLOAT`: Increment a key's floating-point value.

## Hashes

- **Similar to**: JSON or objects.
- **Use cases**: Rate limiting, session cache.
- **Terms**: Key (name of object), field (variable name for value), value (value of field).
- **Time complexity**: O(n) for `HGETALL` and `HSCAN`, O(1) for others.

### Commands

- `HSET`, `HMSET`, `HSETNX`: Set fields in a hash.
- `HGETALL`, `HSCAN`, `HGET`, `HMGET`: Get fields from a hash.
- `HINCRBY` and `HINCRBYFLOAT`: Increment fields in a hash.
- `HDEL`: Delete fields from a hash.
- `HEXISTS`: Check if a field exists in a hash.
- `HKEYS` and `HVALS`: Get all keys or values from a hash.

## Lists

- **Ordered collection** of strings.
- **Use cases**: Activity streams, IPC.
- **Operations**: Add or remove elements from both ends, add relative to another, implement stacks and queues.

### Commands

- `RPUSH` and `LPUSH`: Add elements to the right or left.
- `RPOP` and `LPOP`: Remove elements from the right or left.
- `LRANGE`: Get items in a range.
- `LLEN`: Get the length of the list.
- `LINDEX` and `LSET`: Get or update an item at a particular index.
- `LINSERT`: Insert an item before or after another item.
- `LREM`: Remove items from a list.
- `LTRIM`: Trim a list to keep only a specified range of elements.
