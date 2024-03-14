build:
	cargo build --release
	rust-objcopy --strip-all target/riscv64gc-unknown-none-elf/release/os1 -O binary target/riscv64gc-unknown-none-elf/release/os1.bin

run: build
	qemu-system-riscv64 \
    -machine virt \
    -nographic \
    -bios default \
    -device loader,file=target/riscv64gc-unknown-none-elf/release/os1.bin,addr=0x80200000

clean:
	cargo clean
	rm -rf target
