#!/usr/bin/env ruby

# Raul de leon hernandez

# 0. Si la establece ninguna variable
variable = ARGV[0]

if variable.nil?
  puts "[ERROR]"
  puts "  Debe introducir los parámetros correctos!"
  puts "  Para ver mas informacion use la sentecia '--help'"
  exit 1

end


# 1. VARIABLE --help


if variable == "--help"
  puts "Usage: "
  puts "        systemctml [OPTIONS] [FILENAME]"
  puts "Options:"
  puts "        --help, mostrar esta ayuda."
  puts "        --version, mostrar información sobre el autor del script"
  puts "                   y fecha de creacion."
  puts "        --status FILENAME, comprueba si puede instalar/desintalar."
  puts "        --run FILENAME, instala/desinstala el software indicado."
  puts "Description:"
  puts "        Este script se encarga de instalar/desinstalar"
  puts "        el software indicado en el fichero FILENAME."
  puts "        Ejemplo de FILENAME:"
  puts "        tree:install"
  puts "        nmap:install"
  puts "        atomix:remove"

  exit 0

end


# 2. VARIABLE --version


if variable == "--version"
  puts "RAÚL DE LEÓN HERNÁNDEZ"
  puts "11/02/2021"
  exit 0
end


# 3. VARIABLE --status


if variable == "--status"
  a = `cat datos.txt`
  b = a.split("\n")
  b.each do |i|
  c = i.split(":")
  d = `whereis #{c[0]} | grep bin | wc -l`.chop
    if d == "1"
      puts "#{c[0]}: (I) installed"
    else
       puts "#{c[0]}: (U) uninstalled"
    end
  end
  exit 0
end

# 4. VARIABLE --run



if variable == "--run"
root = `whoami | grep root | wc -l`.chop
  if root == "1"
    a = `cat instalar`
    b = a.split("\n")
    b.each do |i|
    c = i.split(":")
    d = "#{c[1]}"
      if d == "install"
        `zypper #{c[1]} -y #{c[0]}`
        puts "Paquete #{c[0]} instalado"
      else
        `zypper #{c[1]} -y #{c[0]}`
         puts "Paquete #{c[0]} eliminado"
      end
    end
  else
    puts "Es necesario que seas usuario ROOT"
    exit 1
  end
exit 0
end







