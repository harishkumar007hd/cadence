
# Interactive Arrow Annotations in GitHub

Below is an example of an interactive arrow with contextual information.

<div style="position: relative; display: inline-block; cursor: pointer;">
    <span style="background-color: pink; color: white; padding: 5px 10px; border-radius: 5px; position: relative;">
        RISC-V Architecture ↗
    </span>
    <div style="visibility: hidden; width: 200px; background-color: black; color: white; text-align: center; padding: 5px; border-radius: 6px; position: absolute; top: -50px; left: 50%; transform: translateX(-50%); opacity: 0; transition: opacity 0.3s;">
        This section discusses the RISC-V implementation details.
    </div>
</div>

## How it Works

Hover over the "RISC-V Architecture" label to see the tooltip with additional context.
