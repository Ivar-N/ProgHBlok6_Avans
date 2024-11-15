----------------------------------------------------------------------------------
-- Company: 
-- Engineer: 
-- 
-- Create Date: 15.11.2024 13:53:33
-- Design Name: 
-- Module Name: Four_bit_adder - Behavioral
-- Project Name: 
-- Target Devices: 
-- Tool Versions: 
-- Description: 
-- 
-- Dependencies: 
-- 
-- Revision:
-- Revision 0.01 - File Created
-- Additional Comments:
-- 
----------------------------------------------------------------------------------


library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

 entity Four_bit_adder is
	Port ( A0 : in STD_LOGIC;
           A1 : in STD_LOGIC;
           A2 : in STD_LOGIC;
           A3 : in STD_LOGIC;
           B0 : in STD_LOGIC;
           B1 : in STD_LOGIC;
           B2 : in STD_LOGIC;
           B3 : in STD_LOGIC;
           Cin : in STD_LOGIC;
           S0 : out STD_LOGIC;
           S1 : out STD_LOGIC;
           S2 : out STD_LOGIC;
           S3 : out STD_LOGIC;
           Cout : out STD_LOGIC);
   END Four_bit_adder;
  

architecture Behavioral of Four_bit_adder is

   COMPONENT FullAdder
    Port ( A : in STD_LOGIC;
           B : in STD_LOGIC;
           Cin : in STD_LOGIC;
           S : out STD_LOGIC;
           Cout : out STD_LOGIC);
   END COMPONENT;
   
   Signal Cout0, Cout1, Cout2: STD_LOGIC;
   
begin

   Fa1: FullAdder PORT MAP(
        A => A0, 
        B => B0,
        Cin => Cin,
        S => S0,
        Cout => Cout0);
    Fa2: FullAdder PORT MAP(
        A => A1, 
        B => B1, 
        Cin => Cout0,
        S => S1, 
        Cout => Cout1
   );
    Fa3: FullAdder PORT MAP(
        A => A2, 
        B => B2, 
        Cin => Cout1,
        S => S2, 
        Cout => Cout2
   );
    Fa4: FullAdder PORT MAP(
        A => A3, 
        B => B3, 
        Cin => Cout2,
        S => S3, 
        Cout => Cout
   );
   


end Behavioral;