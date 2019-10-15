# Selecting RGA Components

To combine both reports, some components must be discarded from the DHA report and the ChemStation report \(e.g. duplicates\). All components which elute prior to the bridge will be automatically discarded from the DHA report. However, for the ChemStation report, all components that the user defines as after the bridge component will be discarded. What the user defines as occuring after the bridge component is called a policy.

The bridging software will automatically detect and populate the list of ChemStation RGA components as the user selects a ChemStation Report. **The user must select an initial ChemStation Report and a bridge component to begin ordering the RGA components** \(see [Add Report Files](add-report-files.md)\). Any components present in the selected ChemStation report but missing from the current policy will be automatically added to the bottom \(ignore section\). A log of the components that are automatically added is kept in `%appdata%\Roaming\component-bridging-gui\found-rga-components.log`. 

### Ordering RGA Components

Click the `Select RGA Components` sidebar item. Components greyed out below the red bar are ignored. To have a particular component ignored/discarded from the output report, simply drag it to below ignore line.  

![](.gitbook/assets/capture%20%281%29.PNG)

Likewise, drag an ignored component above the bridge component to include it in the output report.

To make a new policy, click the `NEW LIST` button. The new list will inherit all components from the default policy, and can be renamed by editing the `Policy Name` text input. To delete a newly created policy, click the `DELETE` button.

### Deleting Components

Components which will no longer be included in the ChemStation report \(e.g. components that were renamed in ChemStation\) can be put in the ignored component section, but this can get cumbersome as as vestigial components pile up. For this reason, a delete button was provided next to the detector name of a particular component. If the user accidentally deletes a component, it will automatically be added again the next time the user drags in a new ChemStation report.

