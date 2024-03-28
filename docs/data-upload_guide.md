# Data upload guide
!!! warning "Please note:"
    This portion of the webpage is still under construction!

## Importing files
For successful data integration into CDD Vault, precise definition of protocol readouts is crucial to ensure accurate variable mapping. Uploads must conform to a **long-skinny format** (_see example image below_), with dedicated columns for RA-######## (_molecule ID_) and corresponding readout values. This structure is essential for correct data mapping and maintaining data integrity in CDD Vault. For further information, consult the [CDD Vault Knowledgebase resource site](https://support.collaborativedrug.com/hc/en-us/articles/214357923-3-Importing-Single-Point-Screening-Data#readout_definition).

![Long-skinny format](assets/images/example_long-skinny_format.png)

!!! info "Jump to:"
    [**CDD Vault's tutorial**](https://support.collaborativedrug.com/hc/en-us/articles/214358183-How-do-I-format-a-file-for-import) on importing files. (Not READDI-AC-specific)
    
    [**READDI-AC-specific step-by-step guide on importing your data**](#step-by-step-guide-on-importing-your-data) on importing files.



<center> _Continue reading along for more details regarding READDI-AC specific data types structure._ </center>

### Tabular data
Your tabular data can either be added as a:

- **Readout definition** _(if your raw dataset does <u>not</U> need further calculations, i.e. EC50 calculation was already conducted, this is the most common readout you will encounter)_
- **Dose-response calculation**
- **Calculated readout definition** 

![CDD Vault Adding Readouts Selection](assets/images/addreadouts.png)

If you have **corresponding non-tabular data files associated with the tabular data**, please follow the guidelines described in the [step-by-step guide on importing your data.]((#step-by-step-guide-on-importing-your-data))

### All other data types
_Ask Ava to clarify how to store other files that are **not** related to the tabular data imported_

- Add as "File" type in **Readout Definition**??

## Setting-up a protocol

!!! info "Jump to:"
    [**CDD Vault's tutorial**](https://support.collaborativedrug.com/hc/en-us/articles/214357923-3-Importing-Single-Point-Screening-Data#protocol_setup) on protocol set-up. (Not READDI-AC-specific)

    For an in-depth explanation of **Protocols**, see [Understanding Protocols](cddvault.md/#understanding-protocols) section. 

### Step-by-step guide on creating a new protocol

+ **Step 1:** Log in to CDD Vault and ensure you have access to the **READDI AViDD** Project (or an ad hoc project specific to your study)
+ **Step 2:** Navigate to the **Explore Data** tab and locate **Create a new protocol** 
    
    ![CDD Vault Add New Protocol](assets/images/addprotocol.jpg)

+ **Step 3:** Double check you're in the correct **Project** and select a protocol template based on your assay by clicking the **Form drop down**. 
_<center> Remember there are 4 protocol templates for READDI-AC. See [READDI-AC Protocol Categories](cddvault.md/#READDI-AC-Protocol-Categories) for more info regarding selecting the appropriate protocol category for your assay type. </center>_
    ![CDD Vault Select Protocol Category](assets/images/protocolcats.png)
+ **Step 4:** Follow this **Protocol Name** nomenclature structure: **INVESTIGATOR LAST NAME** - **VIRUS TARGET** - **ASSAY TITLE**

    !!! note "Protocol Name Example"
        Arrowsmith - SARS2 nsp 13 ATPase - Dose-Reponse

+ **Step 5:** Fill out the rest of the form, ensuring the required(*) fields are complete, but the more info the better!
+ **Step 6:** Attach SOP using the **Upload a file** button. 
        
    ![CDD Vault Attach SOP](assets/images/SOPattachment.png)

+ **Step 7:** Click **Create Protocol**
        
    ![CDD Vault Attach SOP](assets/images/createprotocol.png)

## Step-by-step guide on setting-up a readout

!!! info "Jump to:"
    [**CDD Vault's tutorial**](https://support.collaborativedrug.com/hc/en-us/articles/214357923-3-Importing-Single-Point-Screening-Data#readout_definition) on setting up a readout. (Not READDI-AC-specific)

    For an in-depth explanation of **Readouts**, see [Understanding Readouts](cddvault.md/#understanding-readouts) section.
### Creating or editing a new readout
+ If you just recently created the protocol, you'll now have the option to assign readouts to your protocol. 

+ If you are adding a new readout to an _**existing** protocol_ you can follow along with these steps as well by first navigating to the protocol and editing the readouts under the **Protocol Details** tab. 
    ![CDD Vault Attach SOP](assets/images/add_edit_readouts.jpg)

!!! info "Remember, there are 3 options for assigning readouts, this guide below will go through all three options."
    [Readout definition](#readout-definition)

    [Dose-response calculation](#dose-response-calculation)

    [Calculated readout definition](#calculated-readout-definition)

#### Readout definition 
Selecting **Add a readout definition** will allow the user to associate the dataset to a defined readout. Note that most data types will fall under this category, e.g., **single-concentration results** (_i.e., % inhibition, titer reduction, % viability_) and **protocol conditions** (_i.e.,concentration, virus, cell line_). 

+ **Step 1**: Add the variable **Name**. 
+ **Step 2**: Select **data type**. For this readout type, there are **5 different data types** that you can select from. _See [Understanding Readouts](cddvault.md/#understanding-readouts) section for more info on data types._ 

    ![CDD Vault readout types](assets/images/datatype_readouts.png)

    + **Number** data types:
        + **Step 2.N.1** Add Unit
        + **Step 2.N.2** Add Display Format: the standard is 3 significant figures
        + **Step 2.N.3** Add description: Note any transformations that your dataset has undergone and other useful information regarding your dataset here. 
        + **Step 2.N.4** Select **Do not normalize this readout**
        + **Step 2.N.5** Don't forget to click **update readout** once complete
    
        **IC50 Readout Example**
        ![CDD Vault Number Readout](assets/images/number_readout.png)
    
    + **Text** data types:
        + guide goes here
    
    + **Pick list** data types:
        + **Step 2.PL.1** click on **Edit Pick List**
        + **Step 2.PL.2** a new light-box window will pop up, where you can manually type values one at a time, or  or copy/paste an entire list of values.
        + **Step 2.PL.3** click **enter** after every manually entered value. Or simply copy/paste a list where entries are placed on different rows.
        + **Step 2.PL.4** click on **update picklist** once complete. 

        **Virus pick list readout example**
        ![CDD Vault Pick List Readout](assets/images/picklist_readout.png)
    
    + **File** data types:
        + guide goes here
    
    + **Batch Link** data types:
        + guide goes here

#### Dose-response calculation
Adding a **dose-response calculation** will present the user with the form shown below to build a calculation using the Levenberg-Marquardt algorithm used to fit a Hill equation to dose-response data. Note that if you already performed calculations **outside** of CDD Vault, then you will <u>**not**</u> use this readout, but instead use the **[add readout definition](#readout-definition)** option.

+ **Step 1**: Fill in the form working from top to bottom. Start by defining the raw data to be imported, followed by data normalization, fit parameters and validation, and finally the calculated end-point. 
+ **Step 2**: Ensure that the **display format** of the data calculations is in **3 significant figures**
+ **Step 3**: Don't forget to click **add/update calculation** at the bottom of the form. 

**Dose-response calculation example**
![CDD Vault Dose-Response Example](assets/images/dose-response_example.png)

#### Calculated readout definition
Calculations are based on existing assay data within your CDD Vault protocols, as well as chemical properties of the registered compounds, and numeric constants. In this manner, you can build dynamic mathematical functions that use protocol readouts as variables, and are automatically updated when new raw data is imported into the Vault.

Calculations are defined as new readouts in existing protocols, based on previously defined readouts. In a new protocol, calculations will be added after the initial set of raw data readout definitions.

+ **Step 1**: Chose to add a calculated readout definition. _Note that if you don't see the formula box as shown below, you do not have access to advanced calculations. [Contact your CDD representative](contact_us.md) or support to enable this._
    ![CDD Vault Add Calculation Example](assets/images/add_calculation.png)
+ **Step 2**: Provide a name for the calculated readout definition (one that does not conflict with any other readout names in this protocol).
+ **Step 3**: Fill in the formula in the provided formula builder.
+ **Step 4**: Always select **average by batch and run** aggregation.
+ **Step 5**: Add description as deemed necessary.
+ **Step 6**: Don't forget to click **update or save calculated readout definition** at the bottom of the form.

**Calculated readout example**
![CDD Vault Calculation Example](assets/images/add_calculation_example.png)

## Step-by-step guide on importing your data

### Readout assignment
Guide on assigning and mapping a readout goes here

## Dataset transformation
Guide on transforming dataset into skinny format goes here
