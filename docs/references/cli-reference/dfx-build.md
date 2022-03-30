# dfx build

Use the `dfx build` command to compile your program into a WebAssembly module that can be deployed on the {IC}. You can use this command to compile all of the programs that are defined for a project in the project’s `dfx.json` configuration file or a specific canister.

Note that you can only run this command from within the project directory structure. For example, if your project name is `hello_world`, your current working directory must be the `hello_world` top-level project directory or one of its subdirectories.

The `dfx build` command looks for the source code to compile using the information you have configured under the `canisters` section in the `dfx.json` configuration file.

## Basic usage

    dfx build [flag] [option] [--all | canister_name]

## Flags

You can use the following optional flags with the `dfx build` command.

<!-- <table>
<colgroup>
<col style="width: 32%" />
<col style="width: 68%" />
</colgroup>
<thead>
<tr class="header">
<th style="text-align: left;">Flag</th>
<th style="text-align: left;">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;"><p><code>--check</code></p></td>
<td style="text-align: left;"><p>Builds canisters using a temporary, hard-coded, locally-defined canister identifier for testing that your program compiles without connecting to the {platform}.</p></td>
</tr>
<tr class="even">
<td style="text-align: left;"><p><code>-h</code>, <code>--help</code></p></td>
<td style="text-align: left;"><p>Displays usage information.</p></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><p><code>-V</code>, <code>--version</code></p></td>
<td style="text-align: left;"><p>Displays version information.</p></td>
</tr>
</tbody>
</table> -->

## Options

You can specify the following option for the `dfx build` command.

<!-- <table>
<colgroup>
<col style="width: 36%" />
<col style="width: 64%" />
</colgroup>
<thead>
<tr class="header">
<th style="text-align: left;">Option</th>
<th style="text-align: left;">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;"><p><code>--network &lt;network&gt;</code></p></td>
<td style="text-align: left;"><p>Specifies the network alias or URL you want to connect to. You can use this option to override the network specified in the <code>dfx.json</code> configuration file.</p></td>
</tr>
</tbody>
</table> -->

## Arguments

You can specify the following arguments for the `dfx build` command.

<!-- <table>
<colgroup>
<col style="width: 36%" />
<col style="width: 64%" />
</colgroup>
<thead>
<tr class="header">
<th style="text-align: left;">Argument</th>
<th style="text-align: left;">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;"><p><code>--all</code></p></td>
<td style="text-align: left;"><p>Builds all of the canisters configured in the project’s <code>dfx.json</code> file.</p></td>
</tr>
<tr class="even">
<td style="text-align: left;"><p><code>canister_name</code></p></td>
<td style="text-align: left;"><p>Specifies the name of the canister you want to build. If you are not using the <code>--all</code> option, you can continue to use <code>dfx build</code> or provide a canister name as an argument (the canister name must match at least one name that you have configured in the <code>canisters</code> section of the <code>dfx.json</code> configuration file for your project.)</p></td>
</tr>
</tbody>
</table> -->

## Examples

You can use the `dfx build` command to build one or more WebAssembly modules from the programs specified in the `dfx.json` configuration file under the `canisters` key. For example, if your `dfx.json` configuration file defines one `hello_world` canister and one `hello_world_assets` canister, then running `dfx build` compiles two WebAssembly modules:

    Unresolved directive in dfx-build.adoc - include::example$sample-dfx.json[]

Note that the file name and path to the programs on your file system must match the information specified in the `dfx.json` configuration file.

In this example, the `hello_world` canister contains the main program code and the `hello_world_assets` canister store front-end code and assets. If you want to keep the `hello_world_assets` canister defined in the `dfx.json` file, but only build the back-end program, you could run the following command:

    dfx build hello_world

Building a specific canister is useful when you have multiple canisters defined in the dfx.json file, but want to test and debug operations for canisters independently.

To test whether a canister compiles without connecting to the {platform} or the local canister execution environment, you would run the following command:

    dfx build --check