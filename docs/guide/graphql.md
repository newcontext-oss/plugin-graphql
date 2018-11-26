# GraphQL Schema

[[toc]]

This plugin has an opinion of how the GraphQL API schema should look like:

- Query name for single record is singular camelCase: `blogPost`.
- Query name for multiple records is plural camelCase: `blogPosts`.
- Multiple records are within a `nodes` object and filtered by a `filter` argument.
- Mutations begin with the verb (`create`, `update`, `delete`) and the camelCased entity: `createBlogPost` for example.
- The create mutation (generated by `$persist`) expects the new record as a input type argument (`createBlogPost(blogPost: BlogPostInput!)`).
- The update mutation (generated by `$push`) expects two arguments: The ID and the new record as a input type  (`updateBlogPost(id: ID!, blogPost: BlogPostInput!)`).
- The delete mutation (generated by `$destroy`) expects the record ID to delete (`deleteBlogPost(id: ID!)`).

You will find concrete examples of the GraphQL queries which are generated by this plugin in the respective chapters of
this documentation. Also we recommend to activate the debug mode of the plugin, which will show you the queries which
are sent.