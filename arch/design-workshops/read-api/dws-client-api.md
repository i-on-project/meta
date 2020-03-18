# Design workshop - Client API #

## Functionality areas
- Catalogue browsing
  - Browse Class and ClassSections
  - Search
  - Linking
- Enroll action
- Enrollment management ("my classes")
  - List
  - Remove
  - Add via catalogue

## Representations

Course:
  - Full and list item
Class:
  - Full and list item
ClassSection:
  - Full and list item



Course
- Acronym 
- One or more Associated Classes (per term)
- Current term class (if there is a current term)

- List representation only contains the acronym

## Documentation

### Public
- media-type
- classes
- properties by class
- link relations
- actions
- fields

### Private
- URIs structures


## URI design

- Stability
- Evolvability

/courses/by-acr/{acr}
/courses/by-id/123

/v0/courses/by-id/123

## Resources

https://github.com/kevinswiber/siren
https://mnot.github.io/I-D/json-home/
https://www.iana.org/assignments/link-relations/link-relations.xhtml
https://tools.ietf.org/html/rfc6570
https://tools.ietf.org/html/rfc7807
https://docs.aws.amazon.com/apigateway/api-reference/resource/
