DISASM_BINARY := calling
DISASSEMBLER := objdump -Mintel
HEXER := hexdump -C
DISASM_OUTPUT_EXTENSION := obj
HEX_OUTPUT_EXTENSION := hex

all: hex disasm

disasm: $(DISASM_BINARY)
	$(DISASSEMBLER) -d $(DISASM_BINARY) > $(DISASM_BINARY).$(DISASM_OUTPUT_EXTENSION)

hex: $(DISASM_BINARY)
	$(HEXER) $(DISASM_BINARY) > $(DISASM_BINARY).$(HEX_OUTPUT_EXTENSION)

$(DISASM_BINARY): $(DISASM_BINARY).go
	go build -gcflags '-N -l' $(DISASM_BINARY).go

clean:
	rm -rf $(DISASM_BINARY) $(DISASM_BINARY).$(DISASM_OUTPUT_EXTENSION) $(DISASM_BINARY).$(HEX_OUTPUT_EXTENSION)
