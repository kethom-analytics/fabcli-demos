# fab-cli-tutorial-lakehouse

Scripts to deploy the [lakehouse tutorial](https://learn.microsoft.com/en-us/fabric/data-engineering/tutorial-lakehouse-introduction) into your Fabric workspace.

This includes:
- 1 workspace
- 1 lakehouse, non-schema
- 2 connections, Blob (public) and ADLS Gen2 (SAS auth)
- 1 external shortcut ADLS Gen2
- 1 pipeline
- 2 notebooks
- 1 semantic model
- 1 Power BI report

## Instructions

Make sure you have the [Fabric CLI](https://aka.ms/FabricCLI) installed:

```bash
$ pip install ms-fabric-cli
```

**Deploy from local**

1. Clone the repository and jump to demo folder
2. Deploy demo
    ```console
    $ ./fab-cli-tutorial-lakehouse/scripts/setup.sh --capacity-name <capacity_name> --postfix 87
    ```

**Deploy using GitHub actions**

1. Fork the repository
2. Create three secrets in your repository: `FAB_TENANT_ID`, `FAB_CLIENT_ID`, and `FAB_CLIENT_SECRET`
3. Go to the Actions tab and set up parameters
4. Run the `deploy-fab-cli-tutorial-lakehouse` workflow
    
## Notes
See notes below for additional info:

- Use `--capacity-name <capacity_name> --postfix 87 --spn_auth_enabled true --upn_objectid <user-objectid>` to deploy using SPN auth from local.
- `upn_objectid` is used to grant user permission during service principal deployment.
- This demo replaced Dataflow Gen2 by Shortcut. The pipeline was modified to create a table.
