<script context="module">
    import { gql, GraphQLClient } from 'graphql-request';

    export const load = async () => {
        const client = new GraphQLClient(
            import.meta.env.VITE_GRAPHQL_API
        )

        const query = gql`
            query geProjects {
                projects {
                    name
                    description
                    sourceCode
                }
            }
        `
        const { projects } = await client.request(query).catch((err) => console.error(err))
        console.log(projects)
        
        return {
            props: {
                projects,
            },
        }
    }
</script>

<script>
    export let projects
</script>

<pre>
    {JSON.stringify(projects, null, 2)}
</pre>
  