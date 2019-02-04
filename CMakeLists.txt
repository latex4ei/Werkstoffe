cmake_minimum_required(VERSION 2.8)

project(Werkstoffe NONE)
include(UseLATEX)

set(IMAGES
    "img/3482353672_892707276f.jpg"
    "img/587px-Alloy_diagram_separate_crystal_building.png"
    "img/Alloy_diagram_limited_mixed_crystal_building.png"
    "img/Alloy_diagram_mixed_crystal_building.png"
    "img/Austauschmischkristall,_kubischflächenzentriert2.svg"
    "img/Austauschmischkristall,_kubischflächenzentriert.svg"
    "img/Austauschmischkristall,_kubischraumzentriert.svg"
    "img/bandstruktur.jpg"
    "img/bcc.pdf"
    "img/capacitor.pdf"
    "img/cat.jpg"
    "img/Density_of_states_in_intrinsic_Semiconductor_DE.svg"
    "img/Density_of_states_in_n-doped_Semiconductor_DE.svg"
    "img/diamond.gif"
    "img/Diamonds_gitter.svg"
    "img/dos.jpg"
    "img/energyband.pdf"
    "img/fcc.pdf"
    "img/H_atom_orbitaly.png"
    "img/hcp.pdf"
    "img/Hexagonal_close_packed.svg"
    "img/Hexagonal_lattice.svg"
    "img/img04.gif"
    "img/inductor.pdf"
    "img/klechkovski.pdf"
    "img/Klechkovski_rule.svg"
    "img/kspace.gif"
    "img/Logo.pdf"
    "img/ls_kopplung_kl.jpg"
    "img/ndotiert.pdf"
    "img/orbitals/"
    "img/period.pdf"
    "img/potentialtopf.png"
    "img/pse.pdf"
    "img/PSE.png"
    "img/qwell.jpg"
    "img/reldie.pdf"
    "img/relDie.svg"
    "img/resistor.pdf"
    "img/sc.pdf"
    "img/sinus.pdf"
    "img/spannung-dehnung.png"
    "img/tetraeder.gif"
    "img/tunnel.png"
)

add_custom_target(
    writegitid ALL
    COMMAND ${CMAKE_CURRENT_SOURCE_DIR}/write-gitid.sh
    WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
)

add_latex_document(
    Werkstoffe.tex
    FORCE_PDF
    IMAGES ${IMAGES}
    DEPENDS writegitid
)
