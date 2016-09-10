# Convert Protobuf to Typescript definition files

Convert this:
```protobuf
message Person {
  string name = 1;
  int32 id = 2;
  bool isFriend = 3;
  repeated PhoneNumber phones = 4;
}

message PhoneNumber {
  string number = 1;
  PhoneType type = 2;
}

message AddressBook {
  repeated Person people = 1;
}
```

into this:

```typescript
interface Person {
  name: string
  id: number
  isFriend: boolean
  phones: PhoneNumber[]
}

interface PhoneNumber {
  number: string
  type: PhoneType
}

interface AddressBook {
  people: Person[]
}
```
