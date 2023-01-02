 # Vault
 
 * Today we are excited to announce the public availability of HashiCorp Vault 1.0. Vault is a tool to manage secrets and protect sensitive data for any infrastructure and application.
 * Many secrets engines create leases for secrets that allow time-limited access to other systems, and in those cases lease_id would contain a lease identifier and lease_duration would contain the length of time for which the lease is valid, in seconds.
 * The path prefix tells Vault which secrets engine to which it should route traffic. For example requests started with secret/  means it will go a secrets engine (by default is kv ).The kv secrets engine reads and writes raw data to the backend storage.
 * When a secrets engine is disabled, all secrets are revoked and the corresponding Vault data and configuration is removed.   
 * Secrets Engine. The read/write/delete/list operations are forwarded to the corresponding secrets engine, and the secrets engine decides how to react to those operations. Ut enables Vault to interface directly with othe system like db or AWS IAM
 * Dynamic Secrets are generated when they are accessed. Unlike the ```kv secrets``` where you had to put data into the store by yourself.
 * A role in Vault is a human-friendly identifier to an action. Vault knows how to create an IAM user via the AWS API, but it does not know what permissions, groups, and policies you want to attach to that user. This is where roles come in - roles map your configuration options to those API calls.
 * AWS secrets engine. Warning: Do not use your root account keys in production   
 * about  lease_id field in the output. This value is used for renewal, revocation, and inspection. Copy this lease_id to your clipboard. Note that the lease_id is the full path, not just the UUID at the end.
 * Authentication. Authentication is the mechanism of assigning an identity to a Vault user.  The access control and permissions associated with an identity are authorization. Authentication is the process by which user or machine-supplied information is verified and converted into a Vault token with matching policies attached.        
    * Vault has pluggable auth methods, making it easy to authenticate with Vault using whatever form works best for your organization. 
 * Token authentication is enabled by default in Vault and cannot be disabled. 
 * Whem you create more tokens, By default, this will create a child token of your current token that inherits all the same policies. The "child" concept here is important: tokens always have a parent, and when that parent token is revoked, children can also be revoked all in one operation
 * In practice, operators should not use the token create command to generate Vault tokens for users or machines. Instead, those users or machines should authenticate to Vault using any of Vault's configured auth methods such as GitHub, LDAP, AppRole, etc
 * Policies in Vault control what a user can access (authorization).
 * The help system may not be the most exciting feature of Vault, but it is indispensable in day-to-day usage  

#### USEFUL COMMANDS
 * ```vault auth list``` command will list all enabled auth methods. 
