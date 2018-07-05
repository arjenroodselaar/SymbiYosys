# BUILD FILE SYNTAX: SKYLARK
python_library(
    name="libSymbiYosys",
    srcs=glob([
        "sbysrc/sby.py",
        "sbysrc/sby_*.py",
    ]),
    base_module="SymbiYosys",
)

python_binary(
    name="sby",
    main_module="SymbiYosys.sbysrc.sby",
    platform="macos-py3",
    deps=[
        ":libSymbiYosys",
    ],
    visibility=[
        "PUBLIC",
    ],
)

command_alias(
    name="job",
    exe=":sby",
    args=[
        #"--yosys " + read_config("sby", "yosys", "yosys"),
        #"--abc " + read_config("sby", "abc", "yosys-abc"),
        #"--smtbmc " + read_config("sby", "smtbmc", "yosys-smtbmc"),
    ],
    env={
        "PYTHONPATH": "{}:$PYTHONPATH".format(read_config(
            "sby",
            "yosys_py3",
            "/usr/share/yosys/python3"))
    },
    visibility=[
        "PUBLIC",
    ],
)
