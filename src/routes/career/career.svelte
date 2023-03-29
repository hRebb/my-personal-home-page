<script>
    import { gql } from 'graphql-request';

    const query = gql`
        query geEvents {
            events {
                name
                date
                description
            }
        }
    `;
</script>