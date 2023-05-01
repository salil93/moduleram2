# moduleram2
module ram2
module ram (
  input wire clk,
  input wire write_en,
  input wire [7:0] addr,
  input wire [7:0] din,
  output reg [7:0] dout
);

  reg [7:0] mem [255:0];

  always @(posedge clk) begin
    if (write_en) begin
      mem[addr] <= din;
    end
    dout <= mem[addr];
  end

endmodule
